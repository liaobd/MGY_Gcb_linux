#定义变量
#ARCH默认为X86，使用gcc编译器，否则使用arm编译器
ARCH ?= x86
TARGET = hello_main

#存放中间文件的路径
BUILD_DIR = build_$(ARCH)
#存放源文件的路径
SRC_DIR = Src
#存放头文件的路径
INC_DIR = Inc .

#源文件，wildcard函数用于获取文件列表
SRCS = $(wildcard $(SRC_DIR)/*.c)
#目标文件
OBJS = $(patsubst %.c, $(BUILD_DIR)/%.o, $(notdir $(SRCS)))
#头文件
DEPS = $(wildcard $(INC_DIR)/*.h)

#指定头文件的路径
CFLAGS = $(patsubst %, -I%, $(INC_DIR))

#根据输入的ARCH变量来选择编译器，默认是x86
ifeq ($(ARCH),x86)
	CC = gcc
else
	CC = arm-linux-gnueabihf-gcc
endif

#默认目标
$(BUILD_DIR)/$(TARGET): $(OBJS)
	$(CC) -o $@ $^ $(CFLAGS)

#*.o文件的生成规则
$(BUILD_DIR)/%.o: $(SRC_DIR)/%.c $(DEPS)
	@mkdir -p $(BUILD_DIR)
	$(CC) -c -o $@ $< $(CFLAGS)

#伪目标
.PHONY:clean
clean:
	rm -rf $(BUILD_DIR)/*.o
