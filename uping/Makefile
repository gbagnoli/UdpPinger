CPPFLAGS=-I/tmp/fbcode_builder_getdeps-ZhomeZgiacomoZworkspaceZfollyZbuildZfbcode_builder/installed/folly/include
THRIFT_GEN+= -Igen-cpp
CPP=g++
LDFLAGS=-g $(THRIFT_GEN) -L/tmp/fbcode_builder_getdeps-ZhomeZgiacomoZworkspaceZfollyZbuildZfbcode_builder/installed/folly/lib
LDLIBS=-lfolly -lgflags -lpthread -lthrift -ldouble-conversion -lglog -ldouble-conversion -levent
THRIFT=thrift

all: uping

uping: AsyncUDPSocket UdpPinger Pinger_types.o
	$(CPP) $(LDFLAGS) $(CPPFLAGS) Pinger_types.o UdpPinger.o AsyncUDPSocket.o Main.cpp -o uping $(LDLIBS)

AsyncUDPSocket: gen-cpp
	$(CPP) $(LDFLAGS) $(CPPFLAGS) -c  AsyncUDPSocket.cpp

UdpPinger: gen-cpp
	$(CPP) $(LDFLAGS) $(CPPFLAGS) -c  UdpPinger.cpp

gen-cpp:
	$(THRIFT) -r --gen cpp Pinger.thrift

Pinger_types.o: gen-cpp
	$(CPP) $(LDFLAGS) $(CPPFLAGS) -c gen-cpp/Pinger_types.cpp

# Pinger_constants.o: gen-cpp
# 	$(CPP) $(LDFLAGS) $(CPPFLAGS) -c gen-cpp/Pinger_constants.cpp

clean:
	rm -f *.o uping
	rm -rf ./gen-cpp
