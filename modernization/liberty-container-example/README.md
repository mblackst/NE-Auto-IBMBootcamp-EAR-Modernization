# LibertyHelloWorld

This is a simple servlet-based web application using IBM WebSphere Liberty and Java 8.

## Requirements

- Java 17+
- Maven
- Liberty Tools Extension in Visual Studio Code

## Build and Run

1. Open this folder in VS Code.
2. Use the Liberty Tools extension to "Start" the server in dev mode.
3. You can also build the WAR file manually:

```bash
mvn clean package
```

4. Deploy the generated `target/HelloWorldServlet.war` to the Liberty server (or dev mode does it automatically).

## Access

Once running, open:

```
http://localhost:9080/HelloWorldServlet/hello
```