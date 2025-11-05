# cpuminer

`cpuminer` 是一个用于莱特币、比特币和其他加密货币的多线程 CPU 挖矿程序。这是 Jeff Garzik 最初的 `cpuminer` 的一个分支。

## 项目概述

该项目是一个命令行工具，允许用户使用其 CPU 挖掘加密货币。它支持莱特币和比特币分别使用的 `scrypt` 和 `sha256d` 哈希算法。该挖矿程序可以使用 Stratum 协议或标准 JSON-RPC 连接到矿池。

## 文件说明

### 核心源文件

*   `cpu-miner.c`: 主源文件，包含作为程序入口点的 `main` 函数。它处理命令行参数解析、线程创建和主挖矿循环。
*   `miner.h`: 主头文件，定义了整个项目中使用的据结构、函数原型和宏。
*   `scrypt.c`: `scrypt` 哈希算法的实现，用于莱特币挖矿。它包括针对各种 CPU 架构的优化版本。
*   `sha2.c`: `sha256d` (双 SHA-256) 哈希算法的实现，用于比特币挖矿。它还包括针对不同 CPU 架构的优化版本。
*   `util.c`: 包含各种实用函数，包括日志记录、JSON-RPC 通信、Stratum 协议处理和命令行解析。

### 构建和配置文件

*   `Makefile.am`: 一个 `automake` 输入文件，定义了项目的编译和链接方式。它指定了 `minerd` 可执行文件的源文件及其依赖项。
*   `configure.ac`: 一个 `autoconf` 输入文件，用于生成 `configure` 脚本。它检查必需的库和系统功能，并设置构建环境。
*   `example-cfg.json`: 一个 JSON 格式的示例配置文件，展示了如何为挖矿程序设置各种选项。

### 其他文件

*   `README`: 原始的 README 文件。
*   `minerd.1`: `minerd` 可执行文件的手册页。
*   `autogen.sh`: 一个用于生成 `configure` 脚本和 `Makefile` 的脚本。
*   `nomacro.pl`: 在构建过程中使用的 Perl 脚本。
*   `.gitignore`: 指定 Git 要忽略的文件和目录。
*   `AUTHORS`, `COPYING`, `ChangeLog`, `NEWS`: 项目信息文件。

## 目录树

```
.
├── .gitignore
├── .idea
│   ├── editor.xml
│   ├── misc.xml
│   ├── vcs.xml
│   └── workspace.xml
├── AUTHORS
├── COPYING
├── ChangeLog
├── Dockerfile
├── LICENSE
├── Makefile.am
├── NEWS
├── README
├── README.md
├── autogen.sh
├── build
├── compat.h
├── compat
│   ├── Makefile.am
│   └── jansson
│       ├── .gitignore
│       ├── LICENSE
│       ├── Makefile.am
│       ├── config.h
│       ├── dump.c
│       ├── hashtable.c
│       ├── hashtable.h
│       ├── jansson.h
│       ├── jansson_private.h
│       ├── load.c
│       ├── strbuffer.c
│       ├── strbuffer.h
│       ├── utf.c
│       ├── utf.h
│       ├── util.h
│       └── value.c
├── configure.ac
├── cpu-miner.c
├── elist.h
├── example-cfg.json
├── miner.h
├── minerd.1
├── nomacro.pl
├── scrypt-arm.S
├── scrypt-ppc.S
├── scrypt-x64.S
├── scrypt-x86.S
├── scrypt.c
├── sha2-arm.S
├── sha2-ppc.S
├── sha2-x64.S
├── sha2-x86.S
├── sha2.c
└── util.c
```