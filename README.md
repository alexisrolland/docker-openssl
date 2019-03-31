# Docker OpenSSL
OpenSSL container to create certificates and keys. It is based on the following tutorial:
https://loglevel-blog.com/how-to-create-self-signed-certificate-with-openssl-and-docker

# Create Docker Container
```
# Change directory to project folder
$ cd docker-openssl

# Build Docker image
$ docker build -t docker-openssl:latest .

# Run Docker container in interactive mode
# Make sure you replace <your_path> with your target folder, this is where files will be created
$ docker run -it --rm -v "C:\your_path:/openssl-certs" docker-openssl
```

# Generate Keys
Once connected to the container, execute the following commands depending on your needs:
```
# Create cert.pem and key.pem files for SSL encryption
req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365
```
