# Java RMI – Remote Method Invocation

A basic Java RMI application where a client invokes the `add()` method of a remote object to add two numbers.

## Project Objective

The project demonstrates **Remote Method Invocation (RMI)**, where an object running in one JVM can invoke a method on an object running in another JVM. The practical uses `add(10, 20)` as the example and returns `30`. fileciteturn3file0L3-L12

## Architecture

```text
                RMI Registry
                     |
                 lookup/bind
                  /       \
                 /         \
          Client JVM     Server JVM
              |               |
            Stub        MyRemote Object
              \               /
               ---- Network ---
                     |
                  Result
```

The RMI architecture in the source includes Client, Server, Remote Interface, Remote Object, RMI Registry, Stub and the server-side dispatch mechanism. fileciteturn3file0L25-L33

## Files

```text
Java-RMI-Calculator/
├── src/
│   ├── MyInterface.java
│   ├── MyRemote.java
│   ├── Server.java
│   └── Client.java
├── README.md
└── .gitignore
```

### MyInterface.java

Defines the remote method:

```java
int add(int a, int b) throws RemoteException;
```

A remote interface extends `java.rmi.Remote` and remote methods normally declare `RemoteException`. fileciteturn3file0L72-L87

### MyRemote.java

Implements the remote interface and extends `UnicastRemoteObject` so the object can receive RMI calls. fileciteturn3file0L250-L271

### Server.java

Creates the remote object and registers it with the RMI Registry using:

```java
Naming.rebind("rmi://localhost/Add", obj);
```

The server then prints `Server is ready...`. fileciteturn3file0L272-L297

### Client.java

Looks up the object using:

```java
Naming.lookup("rmi://localhost/Add");
```

and invokes:

```java
int result = obj.add(10, 20);
```

The expected result is `30`. fileciteturn3file0L298-L325

## How to Run

The source practical uses `localhost`, so both client and server can initially be run on the same computer. fileciteturn3file0L217-L225

### 1. Compile

From the project root:

```bash
javac src/*.java
```

### 2. Start RMI Registry

Open another terminal in the same folder:

```bash
cd src
start rmiregistry
```

On systems where `start` is not available, run:

```bash
rmiregistry
```

### 3. Start Server

Open another terminal:

```bash
cd src
java Server
```

Expected:

```text
Server is ready...
```

### 4. Start Client

Open another terminal:

```bash
cd src
java Client
```

Expected:

```text
Result = 30
```

The supplied practical lists the same execution sequence: compile → start RMI Registry → start Server → start Client. fileciteturn3file0L327-L345

## Important RMI Methods

### `Naming.rebind()`

Registers a remote object with a name.

```java
Naming.rebind("rmi://localhost/Add", obj);
```

### `Naming.lookup()`

Finds the remote object registered with a name.

```java
Naming.lookup("rmi://localhost/Add");
```

These are the two key registry operations described in the source. fileciteturn3file0L385-L404

## RMI Communication Flow

```text
Client calls add(10,20)
        ↓
Client Stub / RMI Runtime
        ↓
Network Request
        ↓
Server JVM
        ↓
MyRemote.add()
        ↓
10 + 20
        ↓
30
        ↓
Client
```

This represents the communication sequence described in the practical. fileciteturn3file0L405-L431

## Advantages

- Easy remote communication
- Normal Java method-call syntax
- Object-oriented approach
- Supports distributed Java applications
- Abstraction from network communication

These advantages are listed in the supplied material. fileciteturn3file0L461-L468

## Limitations

- Mainly suitable for Java-to-Java communication
- Network failures can occur
- Remote calls are slower than local calls
- Configuration can be more complicated
- Client and server must agree on the remote interface fileciteturn3file0L469-L474

## GitHub Upload

Recommended repository name:

**Java-RMI-Calculator**

```bash
git init
git add .
git commit -m "Add Java RMI remote method invocation project"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

## Expected Output

Server:

```text
Server is ready...
```

Client:

```text
Result = 30
```
