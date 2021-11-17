
CFLAGS=-I /usr/local/neuware/include/ -g  -std=c++11
CXXFLAGS=$(CFLAGS) `pkg-config opencv4 --cflags`
LDFALGS=-L /usr/local/neuware/lib64
LDFALGS+=-L /usr/lib/x86_64-linux-gnu/ `pkg-config --libs opencv4`
CXX=g++

SRCS=$(wildcard *.cpp)
OBJS=$(SRCS:%.cpp=%.o)
TARGET=cnrt_resnet50_demo

all:$(TARGET)
$(TARGET):$(OBJS)
	$(CXX) -o $@ $(OBJS) $(LDFALGS) -lcnrt -lcndrv -lpthread -lopencv_core -lopencv_highgui -lopencv_imgproc -lopencv_video
	
clean:
	rm  -f $(TARGET) $(OBJS)
