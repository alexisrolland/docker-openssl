# Docker OpenSSL

OpenSSL container to create certificates and keys. This allows you to use OpenSSL without needing to install it on your computer and regardless of your operating system (Linux or Windows). It is based on the following tutorial:
https://loglevel-blog.com/how-to-create-self-signed-certificate-with-openssl-and-docker

# Requirement

Docker must be configured to run Linux Docker containers. If it's not the case already, right click on the Docker icon and then click on "Switch to Linux containers...".

# Create Docker Container

```shell
# Change directory to project folder
$ cd docker-openssl

# Build Docker image
$ docker build -t docker-openssl:latest .

# Run Docker container in interactive mode
# Make sure you replace `<your_path>` with your target folder, this is where files will be created.

# For Docker Desktop (Windows Pro)
$ docker run -it --rm -v "C:\your_path:/openssl-certs" docker-openssl

# For Docker Toolbox (Windows Home)
$ docker run -it --rm -v "/c/your_path:/openssl-certs" docker-openssl
```

# Generate Keys

Once connected to the container, execute the following commands depending on your needs:

```shell
# Create cert.pem and key.pem files for SSL encryption
$ req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365

# You have some other commands in mind?
# Feel free to do a pull request
```
