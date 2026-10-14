# Linux 学习产物（嵌入式方向补课）

## 项目目标

把「会敲命令」变成「能在 Linux 下把 C 工程从源码编到可执行」：

- 第 1 章：命令行基础——`ls` / 管道 `|` / 重定向 `>` `<` / `grep` / 路径与权限
- 第 2 章：从源码到程序——gcc 编译四步 `-E` `-S` `-c` `-o`、`-Wall` 警告、Makefile、多文件工程（头文件与模块化）
- 第 3 章：把 STM32 项目的一个模块（calc）搬到 Linux 下编译运行

## 怎么编译运行

环境：WSL2 (Ubuntu) + gcc + make。

```bash
# 第一个程序：编译四步，逐步观察中间产物
cd /mnt/d/AI-Work/学习/linux/hello
gcc -E hello.c -o hello.i
gcc -S hello.i -o hello.s
gcc -c hello.s -o hello.o
gcc hello.o -o hello
./hello

# 多文件工程：一条 make 搞定
cd /mnt/d/AI-Work/学习/linux/project
make
./app
```

## 已知局限

- 产物只在 WSL2 (x86-64) 下编译运行，未覆盖交叉编译到 ARM
- calc 模块是逻辑搬运，未接 STM32 硬件（硬件侧在 smart_watch 仓库）
- GitHub 账号改名 qiming-dev 未做（remote 同步待办）；线上推送因代理未开顺延
