# Introduction

Practice for Docker build and push of an image.
Using Dockerfile to replace the default Nginx `index.html`.

# Usage

```
// Build image and tag with "{user}/{image_name}:{version}"
docker image build -t ysfang82/nginx-replace-index:latest .

// Push to Docker Hub
docker image push ysfang82/nginx-replace-index

// Remove local cached image
docker image rm ysfang82/nginx-replace-index

// Run the container
docker container run -d --rm -p 80:80 ysfang82/nginx-replace-index

// Check result
curl localhost
```