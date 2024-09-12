# k8s-demo
Run in project

1. Create a Dockerfile for a static website (HTML/JS/CSS)

Dockerfile
```
# Use the official Nginx image as the base image
FROM nginx:alpine

# Set the working directory to /usr/share/nginx/html
WORKDIR /usr/share/nginx/html

# Copy your local static files to the container
COPY . .

# Expose port 80
EXPOSE 80

# Nginx will serve your static files by default, no additional CMD needed
```
2. Push the Image to a Container Registry (Recommended)
```
docker tag falling-leaves-v1 your-dockerhub-username/falling-leaves-v1:latest

docker push your-dockerhub-username/falling-leaves-v1:latest
```
Build the Image in Minikube’s Docker Daemon: Now, rebuild the Docker image using Minikube’s D>
```
docker build -t falling-leaves-v1 .
```
3. Test it locally
```
docker run -p 8080:80 my-simple-js-app
```
Then, open http://localhost:8080 in your browser to see your JavaScript project running insid>

4. Deploy to Kubernetes

You can now push this image to Docker Hub (or any registry) and deploy it to Kubernetes in th>

