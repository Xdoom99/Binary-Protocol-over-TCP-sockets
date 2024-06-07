The provided code implements a basic echo server using TCP sockets, suitable for handling binary protocols. The server is set up to listen on port 8080 and can handle multiple client connections sequentially. When a client connects, the server reads data sent by the client, prints the number of bytes received, and then echoes the same data back to the client. This echo functionality can handle binary data, making the server useful for testing and debugging binary protocols.

The main function initializes the server by creating a socket, binding it to the specified port, and listening for incoming connections. It continuously accepts new client connections, and each connection is processed by the handle_client function. This function reads data from the client into a buffer, prints the received data length, and sends the same data back to the client, effectively echoing it.

Below is a README.md file for the given C code, along with instructions on how to compile and run the server. This will be suitable for a GitHub repository.

markdown

# Simple Echo Server in C

This repository contains a simple echo server implemented in C. The server listens for incoming TCP connections on port 8080 and echoes back any data it receives from the clients.

## Features

- Listens for incoming TCP connections on port 8080.
- Echoes back any data received from the client.
- Handles multiple client connections sequentially.

## Prerequisites

- GCC (GNU Compiler Collection)
- `make` (Optional, for using the provided Makefile)

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/simple-echo-server.git
    cd simple-echo-server
    ```

2. Compile the server:
    ```sh
    gcc -o echo_server server.c
    ```

    Alternatively, you can use the provided Makefile:
    ```sh
    make
    ```

## Usage

1. Run the server:
    ```sh
    ./echo_server
    ```

    The server will start listening on port 8080. 

2. Connect to the server using `telnet` or `nc` (netcat):
    ```sh
    telnet localhost 8080
    ```

    or

    ```sh
    nc localhost 8080
    ```

3. Type any message and see it echoed back by the server.

## File Structure

- `server.c`: The main server implementation.
- `Makefile`: A Makefile to compile the server.

## Example

### Running the Server

```sh
$ ./echo_server
Server listening on port 8080
Accepted connection from 127.0.0.1:54321
Received 5 bytes
Hello
Received 6 bytes
World!

Connecting to the Server

sh

$ telnet localhost 8080
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
Hello
Hello
World!
World!

License

This project is licensed under the MIT License. See the LICENSE file for details.

makefile


### Instructions to Add the `Makefile`

To make it even easier to compile the server, you can add a `Makefile` to the repository:

```makefile
# Makefile for simple echo server

CC = gcc
CFLAGS = -Wall -Wextra -pedantic -std=c99
TARGET = echo_server
SRCS = server.c

all: $(TARGET)

$(TARGET): $(SRCS)
	$(CC) $(CFLAGS) -o $(TARGET) $(SRCS)

clean:
	rm -f $(TARGET)

Instructions to Add the LICENSE

You can add a LICENSE file to specify the license for your project. Here is an example of the MIT License:

markdown

MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

