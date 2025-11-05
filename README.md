# cpuminer

`cpuminer` is a multi-threaded CPU miner for Litecoin, Bitcoin, and other cryptocurrencies. This is a fork of the original `cpuminer` by Jeff Garzik.

## Project Overview

This project is a command-line tool that allows users to mine cryptocurrencies using their CPU. It supports the `scrypt` and `sha256d` hashing algorithms, used by Litecoin and Bitcoin, respectively. The miner can connect to mining pools using either the Stratum protocol or standard JSON-RPC.

## File Descriptions

### Core Source Files

*   `cpu-miner.c`: The main source file containing the `main` function, which is the entry point of the program. It handles command-line argument parsing, thread creation, and the main mining loop.
*   `miner.h`: The main header file, defining data structures, function prototypes, and macros used throughout the project.
*   `scrypt.c`: Implementation of the `scrypt` hashing algorithm, used for Litecoin mining. It includes optimized versions for various CPU architectures.
*   `sha2.c`: Implementation of the `sha256d` (double SHA-256) hashing algorithm, used for Bitcoin mining. It also includes optimized versions for different CPU architectures.
*   `util.c`: Contains various utility functions, including logging, JSON-RPC communication, Stratum protocol handling, and command-line parsing.

### Build and Configuration Files

*   `Makefile.am`: An `automake` input file that defines how the project is compiled and linked. It specifies the source files for the `minerd` executable and its dependencies.
*   `configure.ac`: An `autoconf` input file that generates the `configure` script. It checks for necessary libraries and system features, and sets up the build environment.
*   `example-cfg.json`: An example configuration file in JSON format, showing how to set various options for the miner.

### Other Files

*   `README`: The original README file.
*   `minerd.1`: The man page for the `minerd` executable.
*   `autogen.sh`: A script to generate the `configure` script and `Makefile`s.
*   `nomacro.pl`: A Perl script used during the build process.
*   `.gitignore`: Specifies files and directories to be ignored by Git.
*   `AUTHORS`, `COPYING`, `ChangeLog`, `NEWS`: Project information files.

## Directory Tree

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