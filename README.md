# 🌍 Nginx AutoIndex Docker Image

## 📖 Overview

This Docker image is based on the official [`nginx:mainline-alpine-slim`](https://hub.docker.com/_/nginx) image and enables the **autoindex** module, allowing directory listing for served files. It provides a lightweight and efficient way to expose files via a web server.

## ⭐ Features

- **AutoIndex Enabled**: Allows directory listing for browsing files.
- **Lightweight**: Based on Alpine Linux for minimal resource usage.
- **Secure & Configurable**: Uses Nginx's default configuration with autoindex enabled.

## 🛠 Cloning and Building Locally

### 🔄 Cloning the Repository

First, clone the repository to your local machine:

```bash
git clone https://github.com/painteau/nginx-autoindex.git
cd nginx-autoindex
```

### 🔨 Building the Custom Image

To create your custom Docker image with autoindex enabled, use:

```bash
docker build -t nginx-autoindex .
```

## 🚀 Running the Container

Once the image is built, you can start a container with:

```bash
docker run -d --name nginx-autoindex \
    -p 8080:80 \
    -v /path/to/your/files:/usr/share/nginx/html:ro \
    nginx-autoindex
```

This will serve the files in `/path/to/your/files` via `http://localhost:8080` with directory listing enabled.

## 📦 Running from the Official Image

If you prefer to use the prebuilt image from GitHub Container Registry, run:

```bash
docker run -d --name nginx-autoindex \
    -p 8080:80 \
    -v /path/to/your/files:/usr/share/nginx/html:ro \
    ghcr.io/painteau/nginx-autoindex:latest
```

## ⚙ Configuration

You can further configure Nginx by mounting a custom configuration file:

```bash
docker run -d --name nginx-autoindex \
    -p 8080:80 \
    -v /path/to/your/files:/usr/share/nginx/html:ro \
    -v /path/to/nginx.conf:/etc/nginx/nginx.conf:ro \
    ghcr.io/painteau/nginx-autoindex:latest
```

## 🌐 Accessing the AutoIndex Page

Once the container is running, open your browser and navigate to:

```
http://localhost:8080
```

You should see a directory listing of the files inside `/path/to/your/files`.

## ⚠ Security Notice

Be cautious when exposing directory listings publicly. Ensure proper access controls are in place if sensitive files are involved.

## 📜 License

This project is open-source and licensed under the MIT License.

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository on GitHub: [painteau/nginx-autoindex](https://github.com/painteau/nginx-autoindex).
2. Create a new branch (`feature-branch`).
3. Commit your changes.
4. Push to your branch and create a pull request.

For major changes, please open an issue first to discuss the proposed modifications.

