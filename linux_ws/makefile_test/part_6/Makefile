#定义变量
ARCH?=x86
TARGET=hello_main
CFLAGS=-I.
DEPS=hello_func.h
OBJS=hello_main.o hello_func.o

ifeq ($(ARCH),x86)
CC=gcc
else
CC=arm-linux-gnueabihf-gcc
endif

#默认目标
$(TARGET):$(OBJS)
	$(CC) -o $@ $^ $(CFLAGS)

#*.o文件的生成规则
%.o:%.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

#伪目标
.PHONY:clean
clean:
	rm -f *.o hello_main
