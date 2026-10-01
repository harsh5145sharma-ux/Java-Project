# Java TCP Client-Server

A basic TCP client-server networking project implemented in Java using the `java.net` and `java.io` packages.

## Project Overview

This project demonstrates communication between two separate Java programs:

- **Server** waits for a client connection on port `5000`.
- **Client** connects to the server using `localhost` and port `5000`.
- The client sends **"Hello Server"**.
- The server receives the message and responds with **"Hello Client"**.
- Both programs close their socket connections after communication.

The supplied practical document describes network programming as communication between computers/processes and specifically uses a Client-Server example with the Java `java.net` package. fileciteturn2file0L3-L10

## Technologies Used

- Java
- TCP (Transmission Control Protocol)
- `java.net`
- `java.io`
- Socket programming

## Project Structure

```text
Java-TCP-Client-Server/
├── src/
│   ├── Server.java
│   └── Client.java
├── README.md
└── .gitignore
```

## Networking Concepts

### Client

A program that requests a service from another program.

### Server

A program that waits for client requests and provides a service.

### IP Address

Identifies a computer or device on a network.

### Port Number

Identifies a specific application/service. This project uses port `5000`.

### Socket

An endpoint used for communication between two programs.

The document defines these terms and shows the communication flow as connection accepted → "Hello Server" → "Hello Client" → close. fileciteturn2file0L12-L28

## TCP

This project uses TCP, which the source document describes as:

- Connection-oriented
- Reliable
- Ordered
- Error-controlled

Java uses `Socket` and `ServerSocket` for TCP communication. fileciteturn2file0L30-L39

## TCP vs UDP

| TCP | UDP |
|---|---|
| Connection-oriented | Connectionless |
| Reliable | Less reliable |
| Ordered data | No guarantee of order |
| Socket/ServerSocket | DatagramSocket |
| More overhead | Less overhead |

These are the TCP/UDP differences listed in the supplied practical document. fileciteturn2file0L40-L52

## How to Run

Make sure Java JDK is installed.

### 1. Compile

From the project root:

```bash
javac src/Server.java src/Client.java
```

### 2. Start Server

```bash
java -cp src Server
```

You should see:

```text
Server started...
Waiting for client...
```

### 3. Open another terminal and start Client

```bash
java -cp src Client
```

Client output:

```text
Connected to server.
Server says: Hello Client
Connection closed.
```

Server output will include:

```text
Client connected.
Client says: Hello Server
Connection closed.
```

The supplied code uses `ServerSocket(5000)`, waits with `accept()`, reads the client message, sends `"Hello Client"`, and closes the connection. fileciteturn2file0L75-L90

## Important Methods

### ServerSocket

```java
ServerSocket serverSocket = new ServerSocket(5000);
```

Creates a server socket listening on port 5000.

### accept()

```java
Socket socket = serverSocket.accept();
```

Waits for an incoming client connection. It is a blocking operation until a client connects. fileciteturn2file0L154-L169

### Client Socket

```java
Socket socket = new Socket("localhost", 5000);
```

Connects the client to the server running locally on port 5000. fileciteturn2file0L96-L114

## GitHub Upload

Create a repository named:

**Java-TCP-Client-Server**

Then run:

```bash
git init
git add .
git commit -m "Add Java TCP client server program"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

## Learning Outcome

This project demonstrates basic Java network programming, TCP communication, socket programming, input/output streams, client-server architecture, and exception handling.
