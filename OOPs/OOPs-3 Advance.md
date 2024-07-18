# String
String objects are immutable. <br>Eg: String str="hello";<br>
str = str+"world" // new object created

As new obj is created every time... string builder/ string buffer is the solution which are mutable.<br>
StringBuilder buff3 = new StringBuilder( "hello" );


# Exception
Exception is an unwanted or unexpected event, which occurs during the execution of a program, i.e. at run time, that disrupts the normal flow of the program’s instructions.

- java.lang.Exception has (e.g. getMessage(), printStackTrace() etc.)
- Java handles exception using five keywords: 
    - **try**:
    - **catch**
    - **finally**
    - **throw**: If we want to manually throw an exception, use keyword throw.
    - **throws**: If a method may cause exception but we do not handle it inside the method
    ```java 
    void f() throws ArithmeticException { . . . }
    ```
    ```java
    try {
        f();
    }
    catch ( Exception e ) {
        System.out.println(“Exception in called method”);
    }
    ```
- We can also create our own custom exception and use it
- We can throw only one exception from a method

### Type of Exception
- Checked / Compile time: notifies at compilation time. Eg: FileNotFoundException, SQLException, etc.
- Unchecked / Runtime: programming bug, invalid input. Eg: ArithmeticException, NullPointerException, etc.
- Errors: beyond the control of the user or programmer

# Networking

- TCP => Connection oriented - Connection is established - Data flows as stream.
- java.net package - for networking. Eg: InetAddress class

## Socket programming: Establishing connection using TCP 
### Server side
- Creating a server socket
```java
ServerSocket server = new ServerSocket ( portNumber, queueLength );
```

- Accepting a connection: server listens indefinitely for an attempt by a client to connect.
```java 
Socket connection = server.accept();
```

- Reading and writing to the socket: 
1. Server sends information to client via Outputstream
2. Server receives information from client via Inputstream
```java
DataInputStream input = new DataInputStream (connection.getInputStream());
DataOutputStream output = new DataOutputStream (connection.getOutputStream());
```
- Closing the connection
```java
input.close();
connection.close();
server.close();
```
---
### Client side
- Creating a socket: Returns a socket if the connection is successful
```java
Socket connection = new Socket (serverAddress,, portNumber);
```
- Reading and writing to the socket
1. Client sends information to server via Outputstream
2. Client receives information from server via Inputstream
```java
DataInputStream input = new DataInputStream (connection.getInputStream());
DataOutputStream output = new DataOutputStream (connection.getOutputStream());
```
- Closing the connection
```java
input.close();
output.close();
connection.close();
```
