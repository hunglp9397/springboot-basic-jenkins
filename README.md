# CI/CD SpringBoot project tích hợp Jenkins

### 1. Cài đặt jenkins(Trên docker)
- `docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v D:\Workspace\docker-volume-data\jenkins-data:/var/jenkins_home jenkins/jenkins:lts`
- Sau khi run container, truy cập _localhost:8080_ để vào jenkins
- Lấy token của jenkins : `docker logs jenkins_container_id`
    + ![1.jpg](guide_img/1.jpg)
- Sau đó lấy token để nhập vào  hệ thống
- Cài đặt ngrok (App dùng để expose localhost jenkins ra một url khác trên internet để có thể truy cập được)
    + ![1.jpg](guide_img/1.jpg)
### 2. Tích hợp Jenkins vào Github
- Tạo project trên github
- Vào Phần settings -> webhook, Nhập url `https://5293-1-55-219-115.ngrok-free.app/github-webhook/`
- ![3.jpg](guide_img/3.jpg)
### 3. Tạo project trên Jenkins
- ![4.jpg](guide_img/4.jpg)
- ![6.jpg](guide_img/6.jpg)
- Sau khi push code lên branch main thì jenkins bắt được events, và đây chính là event push:
    + ![5.jpg](guide_img/5.jpg)
- **_Giải thích_**: Jenkins clone source code và đẩy vào thư mục _/var/jenkins_home/workspace/springboot-basic-jenkins_ trong jenkins containers
    + ![7.jpg](guide_img/7.jpg)
    +  ![8.jpg](guide_img/8.jpg)
### 4. Cách thứ 2 để tích hợp Jenkins vào Gitub : Sử dụng Jenkinfile
- Trong thư mục gốc của project, tạo file Jenkinsfile, cấu hình stages và link github
- Ví dụ như sau:
           
   

      