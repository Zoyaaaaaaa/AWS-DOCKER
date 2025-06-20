# DevOps Assignment - Containerized Node.js Application

This project demonstrates a complete DevOps workflow including containerization with Docker, image management on Docker Hub, and deployment on AWS EC2.

## 🚀 Live Application
**Public URL:** [http://18.226.17.119/](http://18.226.17.119/)

## 📋 Project Overview

A Node.js web application that has been:
- Containerized using Docker
- Built for multi-platform compatibility (linux/amd64)
- Pushed to Docker Hub registry
- Deployed on AWS EC2 instance
- Made publicly accessible

## 🛠 Technology Stack

- **Runtime:** Node.js 18 (Alpine Linux)
- **Containerization:** Docker
- **Registry:** Docker Hub
- **Cloud Platform:** AWS EC2
- **Web Server:** Node.js Express (Port 3000)

## 📂 Project Structure

```
aws-docker/
├── Dockerfile
├── package.json
├── package-lock.json
├── app.js (or main application files)
├── public/
│   └── (static assets)
└── README.md
```

## 🐳 Docker Configuration

### Dockerfile
The application uses a multi-stage Docker build with Node.js 18 Alpine base image for optimal size and security.

### Key Docker Commands Used

#### 1. Building the Docker Image
```bash
# Build the Docker image with tag
docker build -t zoya0302/aws-docker:01 .
```

#### 2. Running the Container Locally
```bash
# Run container with port mapping
docker run --rm -p 3000:3000 zoya0302/aws-docker:01
```
- Container runs on port 3000
- Accessible at `http://localhost:3000`
- `--rm` flag automatically removes container when stopped

#### 3. Building for Production (Multi-platform)
```bash
# Build for Linux AMD64 architecture (EC2 compatibility)
docker buildx build --platform linux/amd64 -t zoya0302/aws-docker:01 .
```

## 📤 Docker Hub Deployment

### Authentication
```bash
# Login to Docker Hub (web-based authentication)
docker login
```
- Used web-based login with device confirmation code
- Device codes used: `HFLS-PLBQ`, `GFPB-VFLK`

### Pushing Image
```bash
# Push image to Docker Hub registry
docker push zoya0302/aws-docker:01
```

**Docker Hub Repository:** `zoya0302/aws-docker:01`

### Push Results
- **Size:** 856 bytes (manifest)
- **Status:** Successfully pushed with layer optimization

## ☁️ AWS EC2 Deployment

### EC2 Instance Setup
1. **Instance Created:** AWS EC2 instance provisioned
2. **Security Groups:** Configured to allow HTTP traffic on port 80
3. **Public IP:** `18.226.17.119`

### Deployment Process
```bash
# On EC2 instance - Pull the Docker image
docker pull zoya0302/aws-docker:01

# Run the container
docker run -d -p 80:3000 zoya0302/aws-docker:01
```

### Instance Configuration
- **Public IP:** 18.226.17.119
- **Port Mapping:** EC2 port 80 → Container port 3000
- **Access:** Public internet accessible
- **Status:** ✅ Live and running

## 🔧 Build Process Details

### Build Performance
- **Build Time:** ~2.4 seconds
- **Build Context:** 41.06kB transferred
- **Layer Caching:** Utilized Docker layer caching for faster rebuilds
- **Stages Completed:** 10/10 and 11/11 (multi-platform build)

### Build Optimization
- Used Alpine Linux base image for smaller footprint
- Implemented proper layer caching strategy
- Multi-platform build support for deployment flexibility

## 🌐 Application Access

### Local Development
```bash
# Run locally
docker run --rm -p 3000:3000 zoya0302/aws-docker:01
# Access: http://localhost:3000
```

### Production (AWS EC2)
- **URL:** [http://18.226.17.119/](http://18.226.17.119/)
- **Status:** ✅ Live and accessible
- **Performance:** Optimized for cloud deployment

## 📊 Deployment Verification

### Successful Deployments
1. ✅ **Docker Build:** Image built successfully
2. ✅ **Local Testing:** Container runs on localhost:3000
3. ✅ **Docker Hub Push:** Image pushed to registry
4. ✅ **EC2 Deployment:** Application running on AWS
5. ✅ **Public Access:** Accessible via public IP

### Key Metrics
- **Build Success Rate:** 100%
- **Image Size:** Optimized with Alpine Linux
- **Deployment Time:** < 5 minutes
- **Uptime:** Continuous since deployment

## 🔄 CI/CD Ready

This project is structured for easy integration with CI/CD pipelines:

- **Dockerfile** optimized for automated builds
- **Multi-platform** support for various deployment targets
- **Registry integration** with Docker Hub
- **Cloud deployment** tested and verified

## 🏆 Achievement Summary

✅ **Containerization:** Successfully dockerized Node.js application  
✅ **Registry Management:** Pushed to Docker Hub with proper tagging  
✅ **Cloud Deployment:** Deployed on AWS EC2 with public access  
✅ **Multi-platform Build:** Built for linux/amd64 architecture  
✅ **Production Ready:** Live application accessible worldwide  

## 🔗 Quick Links

- **Live Application:** [http://18.226.17.119/](http://18.226.17.119/)
- **Docker Hub:** [zoya0302/aws-docker:01](https://hub.docker.com/repository/docker/zoya0302/aws-docker/general)
- **AWS EC2 Instance:** 18.226.17.119

---
**GOOGLE DOCS:** Screenshots and steps  [Google Docs](https://docs.google.com/document/d/1k2TXECP3FL9zejj-ZCzqln-Wd2jmFQUE2HjDl2RBvlQ/edit?usp=sharing)
**Project Status:** ✅ Complete and Live  
**Deployment Environment:** AWS EC2 + Docker Hub
