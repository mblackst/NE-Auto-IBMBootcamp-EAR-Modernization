# 🐳 Running Liberty Hello World with Podman

This guide walks you through setting up Podman, building your Liberty Hello World servlet, and running it inside a container.

---

## 📦 Prerequisites

- A working Maven project (e.g. LibertyHelloWorld)
- `Dockerfile` that uses a valid Liberty base image
- Podman installed

---

## 🧰 Step 1: Initialize and Start Podman Machine

If you're on macOS or Windows, Podman runs inside a lightweight VM.

```bash
# One-time setup
podman machine init

# Start the VM
podman machine start
```

---

## 🛠️ Step 2: Build the WAR File

From the root of your Liberty project:

```bash
mvn clean package
```

This creates the WAR at:

```
target/HelloWorldServlet.war
```

---

## 🐧 Step 3: Create a Dockerfile

Make sure your project root contains a file named `Dockerfile`:

```Dockerfile
FROM icr.io/appcafe/open-liberty:full-java17-openj9-ubi

COPY src/main/liberty/config/ /config/
COPY target/HelloWorldServlet.war /config/dropins/

EXPOSE 9080
```

---

## 🔨 Step 4: Build the Container Image

```bash
podman build -t liberty-helloworld .
```

---

## 🚀 Step 5: Run the Container

```bash
podman run -d -p 9080:9080 --name liberty-hello liberty-helloworld
```

- `-d`: Run detached
- `-p 9080:9080`: Map container port 9080 to local port
- `--name liberty-hello`: Name of your container

---

## 🌐 Step 6: Access the Application

Once the container is running, open your browser and go to:

```
http://localhost:9080/HelloWorldServlet/hello
```

You should see:

```
Hello, World from IBM WebSphere!
```

---

## 🛑 Stopping the Container

```bash
podman stop liberty-hello
podman rm liberty-hello
```

---

## 🧼 Optional Cleanup

```bash
podman rmi liberty-helloworld
podman machine stop
```

---

## 🧵 Related Resources

- [Open Liberty Container Docs](https://openliberty.io/docs/latest/container-images.html)
- [IBM Container Registry](https://www.ibm.com/cloud/container-registry)