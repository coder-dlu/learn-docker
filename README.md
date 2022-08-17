# learn-docker
# 1: Dockek là gì?
- docker là ứng dụng mã nguồn mở.nó giúp cho chúng ta tạo ra các container để chúng ta phát triển triển khai ứng dụng. Hay có thể hiểu là nó cho ứng dụng chạy trong môi trường cách ly gọi là container.Chúng ta có thể xem container như là một máy ảo.
- Đây là mô hình mô tả hoạt động của docker:

![Container](container.PNG)

=> Chúng ta có một máy vật lý trong(hay còn gọi là máy host) chúng ta dùng để cài docker. Khi docker chạy chúng ta muốn chạy một ứng dụng nào đó chạy trên môi trường của docker thì docker sẽ tạo ra một môi trường cách ly gọi là container. Trong các container nó chứa đầy đủ các thư viện, các gói ứng dụng nhằm đảm bảo cho ứng dụng của chúng ta hoạt động được trong docker. Docker có thể tạo ra nhiều container để chạy nhiều ứng dụng khác nhau. Giữa các container sẽ cách ly với nhau nên nó không có tương tác trực tiếp qua lại với nhau. Nó tương tự như việc chúng ta cài các máy ảo khác nhau dể chạy các ứng dụng khác nhau.
- VMs với Docker

![Container](VMs_Docker.PNG)

# 2: Lệnh sử dụng docker
-  Image trong docker là những phần mềm được đóng gói và quản lý bởi docker.
-  Ví Dụ:
  + Images đóng gói hệ điều hành PHP
  + Images đóng gói Hệ điều hành Ubuntu

![Container](image_container.PNG)

Trong các Images nó chỉ đọc không thể sửa đổi. Khi Images được docker khởi chạy thì phiên bản của Images được gọi là các container. Các container có thể ghi được dữ liệu vào trong đó
  - Để kiểm tra xem docker có những images nào chúng ta sử dụng lệnh: docker images(Mở Windows powerShell)

![Container](dockerImage.PNG)

Chú thích: REPOSITORY là tên của image, TAG là phiên bản của image, IMAGE ID: mã của Image, CREATE: ngày tạo,SIZE: kích thước image

Có thể Xem các Image của docker tại đây: https://hub.docker.com/search?q=image&type=image
- Có thể tìm kiếm image trên Windows powerShell theo cú pháp: docker search keyword

![Container](searchImage.PNG)

  - Muốn cài đặt một image ta sử dụng câu lệnh: docker pull image:tag

![Container](pull.PNG)

  - Muốn cài đặt một image với phiên bản mới nhất ta sử dụng câu lệnh: docker pull image:latest hoặc docker pull image
  - Muốn xóa một image ta sử dụng câu lệnh: docker image rm image:Tag hoặc docker image rm IMAGE ID
    + IMAGE ID trong phần chạy docker images

![Container](rm.PNG)

  - Muốn chạy một Image chúng ta sử dụng lệnh sau: docker run -it ubuntu:latest hoặc docker run -it IMAGE ID
    + IMAGE ID trong phần chạy docker images

![Container](run.PNG)
 
Chúng ta chạy ubuntu với tài khoản root hostname là 19fe4676620d.
- Chúng ta có thể kiêm tra thông tin của ubuntu này như sau:

![Container](info.PNG)

  - Kiêm tra các các container đang chạy sử dụng docker ps và tất cả container đang có là docker ps -a

![Container](ps.PNG)

  - Chạy container sử dụng:  docker start CONTAINER ID hoặc  docker start NAMES

![Container](start.PNG)

  - tắt container sử dụng:  docker stop CONTAINER ID hoặc  docker stop NAMES

![Container](stop.PNG)

  - Chạy container có host do chúng ta tạo ra: 

![Container](host.PNG)
![Container](host1.PNG)


```Dockerfile
Tóm tắt các lệnh làm quen

#kiểm tra phiên bản
docker --version

#liệt kê các image
docker images -a

#xóa một image (phải không container nào đang dùng)
docker images rm imageid

#tải về một image (imagename) từ hub.docker.com
docker pull imagename

#liệt kê các container
docker container ls -a

#xóa container
docker container rm containerid

#tạo mới một container
docker run -it imageid 

#thoát termial vẫn giữ container đang chạy
CTRL +P, CTRL + Q

#Vào termial container đang chạy
docker container attach containerid

#Chạy container đang dừng
docker container start -i containerid

#Chạy một lệnh trên container đang chạy
docker exec -it containerid command
```

https://www.youtube.com/watch?v=Bemy5gBjZrE&list=PLWBrqglnjNl3TDF6WKpAl4maE3yJ5CpYF
## 3.Làm việc với Docker Image,Container,kết nối SQL Server
