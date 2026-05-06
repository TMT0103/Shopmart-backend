# 🚀 E-commerce Backend (Spring Boot)

## 📌 Giới thiệu

Backend cho hệ thống thương mại điện tử, xây dựng bằng **Spring Boot + PostgreSQL + JWT Authentication**.

### 🔥 Chức năng chính

* 🔐 Đăng ký / đăng nhập (JWT)
* 👤 Quản lý người dùng (User / Admin)
* 📦 Quản lý sản phẩm
* 🗂️ Quản lý danh mục
* 🛒 Giỏ hàng
* 📑 Đơn hàng (Order + Order Detail)
* ☁️ Upload ảnh (Cloudinary)

---

## 🛠️ Công nghệ sử dụng

* Java 17+
* Spring Boot
* Spring Security + JWT
* PostgreSQL
* JPA / Hibernate
* Cloudinary

---

## ⚙️ Cài đặt & chạy project

### 1️⃣ Clone project

```bash
git clone https://github.com/your-username/ecommerce-backend.git
cd ecommerce-backend
```

---

### 2️⃣ Tạo file cấu hình

📌 **Quan trọng:** File `application.yml` đã được ignore trong `.gitignore`

👉 Tạo file:

```bash
src/main/resources/application.yml
```

👉 Nội dung:


server:
  port: 8080

spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/ecommerce
    username: your_username
    password: your_password

  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true

cloudinary:
  cloud-name: your_cloud_name
  api-key: your_api_key
  api-secret: your_api_secret

app:
  jwt:
    secret: your_jwt_secret
    expiration-ms: 86400000




 3️⃣ Chạy database

Tạo database PostgreSQL:

sql
CREATE DATABASE ecommerce;


---

### 4️⃣ Run project

```bash
./mvnw spring-boot:run
```

hoặc chạy trực tiếp trong IDE

---

## 🔐 Authentication

### 📥 Login


POST /auth/login


Response:

json
{
  "token": "JWT_TOKEN"
}


👉 Lưu token và gửi trong header:

http
Authorization: Bearer <token>


---

## 📦 API chính

### 🛍️ Product

* `GET /products` – xem sản phẩm
* `POST /products` – thêm (ADMIN)
* `PUT /products/{id}` – sửa (ADMIN)
* `DELETE /products/{id}` – xoá (ADMIN)

---

### 🗂️ Category

* `GET /category`
* `POST /category` (ADMIN)
* `PUT /category/{id}` (ADMIN)
* `DELETE /category/{id}` (ADMIN)

---

### 🛒 Cart

* `GET /cart`
* `POST /cart/add`
* `PUT /cart/update`
* `DELETE /cart/remove`

---

### 📑 Orders

* `POST /orders/checkout`
* `GET /orders`
* `GET /orders/{id}`
* `PUT /orders/{id}/status` (ADMIN)

---

## 🔑 Role

* `ROLE_USER`
* `ROLE_ADMIN`

---



## 👨‍💻 Author

* Minh Tuấn Trần

---
