CPPFLAGS=-I/tmp/fbcode_builder_getdeps-ZhomeZgiacomoZworkspaceZfollyZbuildZfbcode_builder/installed/folly/include
THRIFT_GEN+= -Igen-cpp
CPP=g++
LDFLAGS=-g $(THRIFT_GEN) -L/tmp/fbcode_builder_getdeps-ZhomeZgiacomoZworkspaceZfollyZbuildZfbcode_builder/installed/folly/lib
LDLIBS=-lfolly -lgflags -lpthread -lglog -ldouble-conversion
THRIFT=thrift

all: upong

upong: NoradTargetThread.o
	$(CPP) $(LDFLAGS) $(CPPFLAGS) NoradTargetThread.o Main.cpp -o upong $(LDLIBS)

NoradTargetThread.o:
	$(CPP) $(LDFLAGS) $(CPPFLAGS) -c  NoradTargetThread.cpp

clean:
	rm -f *.o upong
