# C

## 编译

### GCC

flowchart LR
	main.c（源文件） --预处理--> main.i （修改后的源文件） --编译-->  main.s（汇编代码） --汇编--> main.o （二进制文件） --连接--> main（可执行文件）

- gcc -E main.c -o main.i
- gcc -S main.i -o main.s
- gcc -c main.s -o main.o
- gcc main.o -o main

## 构建

### Make

- MakeFile

  格式：
  targets : prerequisites
  	command1
  	command2
  	...
  
  例：
  ```Makefile
  main.exe : main.o test.o
  
  main.o : main.c
  	gcc -E main.c -o main.i
  	gcc -S main.i -o main.s
  	gcc -c main.s -o main.o
  test.o : test.c
  	gcc -E test.c -o test.i
  	gcc -S test.i -o test.s
  	gcc -c test.s -o test.o
  ```
  
- mingw32-make.exe

### Cmake

- CMakeLists.txt

  跨平台生成Makefile
  
  格式：
  ```CMake
  cmake_minimum_required(VERSION 3.22) // Cmake 版本
  project(untitled C) // 使用的语言为C
  
  set(CMAKE_C_STANDARD 99) // 使用的C的标准
  
  add_executable(untitled main.c test.c test.h) // 项目名称和要编译的源文件列表
  ```
  
- cmake -S . -B test -G "MinGW Makefiles"

  -S：Source
  -B：Binary，要生成的二进制文件的文件名
  -G：Generator，生成器
  
  
## 调试

### LLDB

- gcc main.c test.c -g -o main

  gcc 编译时添加-g可以附加调试信息，之后才可以对二进制文件进行调试
  
  
- 命令

	- r：运行
	- b 10：对第10行打断点
	- c：继续往后执行
	- v：查看当前所有变量
	- q：结束

### GBD

## 文件读写

### 随机读写

- 子主题 1

