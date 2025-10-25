# 🐳 Apache Webserver Docker Project
- Create a Docker hub public repository
- Containerize our Apache webserver
- Upload image to your docker hub
- Have a friend from your cluster to pull your image and build it.
### 🎯 Objective
Containerize an Apache webserver and deploy it using Docker.

### 🧱 Steps
1. Built a Docker image using Apache HTTPD base.
2. Copied a custom HTML homepage.
3. Tested locally with port mapping.
4. Pushed to Docker Hub:  
   👉 [https://hub.docker.com/r/anslem2025/apache-webserver](https://hub.docker.com/r/anslem2025/apache-webserver)
## 🧩 Step-by-Step Plan 
### 🚀 Step 1 — Launch EC2 Instance
Am using and ubuntu server which i will use session manager for this  work.

<img width="1920" height="932" alt="Screenshot (675)" src="https://github.com/user-attachments/assets/021f9e3c-dda8-49bc-a1b5-9b62db46510d" />

### 🐳 Step 2 — Install Docker
<img width="1920" height="926" alt="Screenshot (676)" src="https://github.com/user-attachments/assets/04420ced-9ebf-42d8-a4a7-bbf765bd4126" />

### 📁 Step 3 — Set up your project folder
```bash
mkdir apache-docker
  cd apache-docker
```
- Create the files:
```bash
apache-docker/
│
├── Dockerfile
└── index.html
```
<img width="1920" height="903" alt="Screenshot (677)" src="https://github.com/user-attachments/assets/abb7fd13-6231-4907-9863-8ddd4b46a5f9" />

### 🧩 Step 4 — Build the Docker image
```bash
docker build -t apache-webserver .
```
<img width="1920" height="901" alt="Screenshot (678)" src="https://github.com/user-attachments/assets/28ff8858-5d6c-4708-9aa0-e312b0787148" />

- used this command to see the just created image: docker images

### 🧪 Step 5 — Run and Test Locally
```bash
docker run -d -p 8080:80 apache-webserver
```
- To see your image runing
```bash
  docker ps
```
<img width="1920" height="942" alt="Screenshot (679)" src="https://github.com/user-attachments/assets/bb47c463-4aef-461a-9eda-9674a61c22cf" />

- Then check browser and visit:public ip or the server

<img width="1920" height="902" alt="Screenshot (682)" src="https://github.com/user-attachments/assets/e5c9ce9a-9046-4aaa-bedc-233e05af3487" />

<img width="1920" height="974" alt="Screenshot (681)" src="https://github.com/user-attachments/assets/cf2d0618-c3f6-456e-ad9e-3c910a3ec508" />

### STEP 6 — Tag and push to Docker Hub
```bash
docker login
```
- Then tag the image and push:
```bash
docker tag apache-webserver yourusername/apache-webserver:latest
docker push yourusername/apache-webserver:latest
```
<img width="1920" height="919" alt="Screenshot (685)" src="https://github.com/user-attachments/assets/55c4b1c5-dc0f-4c21-902b-698f8093f7c3" />

- Verify on Docker Hub

<img width="1920" height="907" alt="Screenshot (686)" src="https://github.com/user-attachments/assets/bca80478-0303-4b41-9ebd-7258992d8270" />

https://hub.docker.com/r/anslem2025/apache-webserver

### 🧑‍🤝‍🧑 Step 7 — Share and Verify
```bash
docker pull yourusername/apache-webserver:latest
docker run -d -p 8080:80 yourusername/apache-webserver:latest
```


## 🧩 Conclusion

This project demonstrated the complete process of containerizing an Apache webserver using Docker on an AWS EC2 instance.
Starting from building a simple HTML webpage, we created a Dockerfile, built a lightweight image, and successfully deployed it as a running container accessible through a web browser.

The custom image — now available publicly on Docker Hub (anslem2025/apache-webserver) — ensures that the application can be easily shared, pulled, and run on any environment without dependency issues.

This exercise clearly highlights the power of Docker in DevOps, showing how containerization improves:

Portability (same image runs anywhere)

Scalability (can deploy multiple containers)

Collaboration (others can pull and use the same image)

Automation readiness (ready for CI/CD pipelines)

By pushing the image to Docker Hub and testing it externally, the deployment lifecycle is complete — proving the practical application of containerization for real-world web applications.








