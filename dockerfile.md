Dockerfile là gì
Là file config dùng để build các image mới dựa trên một image có sẵn

Các lệnh trong Dockerfile
FROM: Lấy 1 image trên docker hub
LABEL: Thông tin người bảo trì dockerfile
ENV: thiết lập một biến môi trường
RUN: Chỉ chạy khi build image, được sử dụng để cài đặt các package vào container
COPY: Sao chép các file và thư mục vào container
ADD: Sao chép các file và thư mục vào container
CMD: trong 1 Dockerfile chỉ có 1 CMD, chỉ chạy khi thực hiện lện docker run để tạo ra 1 container
WORKDIR: Thiết lập thư mục làm việc cho các chỉ thị khác như: RUN, CMD, ENTRYPOINT, COPY, ADD,…
ARG: Định nghĩa giá trị biến được dùng trong lúc build image
ENTRYPOINT: cung cấp lệnh và đối số cho một container thực thi
EXPOSE: khai báo port lắng nghe của image
VOLUME: tạo một điểm gắn thư mục để truy cập và lưu trữ data.
