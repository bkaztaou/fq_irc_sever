# fq_irc_sever

A minimal IRC server written in C++98.

This project implements the core of the IRC protocol: client registration with a password, nicknames, usernames, and message routing between connected clients. It follows the structure of the classic 42 school "ft_irc" assignment, using a single event loop to handle every connection without threads or forking.

## Features

* TCP server that accepts and manages multiple simultaneous clients
* Password protected connections
* Registration flow using PASS, NICK, and USER
* Parsing of IRC style commands sent over plain text
* Non blocking I/O handled through a single polling loop

## Project structure

```
fq_irc_sever
├── include
├── src
├── main.cpp
└── Makefile
```

* `include` holds the header files that declare the server, client, and command handling classes
* `src` holds the corresponding implementation files
* `main.cpp` is the entry point that reads the command line arguments and starts the server
* `Makefile` builds the project

## Requirements

* A C++98 compatible compiler (the project is built with `c++`)
* A Unix like environment (Linux or macOS)
* `make`

## Building

Clone the repository and run make from the project root.

```
git clone https://github.com/bkaztaou/fq_irc_sever.git
cd fq_irc_sever
make
```

This produces an executable named `ircserv`.

Other available targets:

```
make clean   # remove object files
make fclean  # remove object files and the executable
make re      # rebuild from scratch
```

## Usage

Run the server with a port and a connection password.

```
./ircserv <port> <password>
```

Example:

```
./ircserv 6667 mypassword
```

## Connecting to the server

You can connect with any standard IRC client, such as irssi or HexChat, or with a simple tool like netcat for quick tests.

Using netcat:

```
nc 127.0.0.1 6667
```

Once connected, register with the standard commands:

```
PASS mypassword
NICK myname
USER myname 0 * :My Real Name
```

## License

No license file is currently included in this repository. Contact the repository owner if you need clarification on usage terms.
