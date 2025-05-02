# HelloWorldServlet

This is a simple Java Servlet application built with Java 8 to run on IBM WebSphere.

## Structure

- `src/com/example/helloworld/HelloWorldServlet.java` – the servlet source code.
- `WebContent/WEB-INF/web.xml` – deployment descriptor.
- `pom.xml` – Maven configuration to build the WAR file.

## Build Instructions

1. Make sure you have Maven installed.
2. Open a terminal in the root of the project folder.
3. Run:

```bash
mvn clean package
```

4. The `target/HelloWorldServlet.war` file will be generated.
5. Deploy this WAR to your IBM WebSphere Application Server.

## URL

Once deployed, access the servlet at:

```
http://<your-server>:<port>/HelloWorldServlet/hello
```