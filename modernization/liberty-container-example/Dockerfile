FROM icr.io/appcafe/open-liberty:full-java17-openj9-ubi

# Copy server configuration
COPY src/main/liberty/config/ /config/

# Add your application
COPY target/HelloWorldServlet.war /config/dropins/

# Expose HTTP port
EXPOSE 9080

