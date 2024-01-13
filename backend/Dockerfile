# เรียกใช้งาน base image ของ Go
FROM golang:latest

# สร้างโฟลเดอร์และเปลี่ยนเป็นไดเร็กทอรีทำงาน
RUN mkdir /test-my-self-react
WORKDIR /test-my-self-react

# คัดลอกไฟล์ go.mod และ go.sum เพื่อติดตั้ง dependencies
COPY go.mod go.sum ./
RUN go mod download

# คัดลอกโค้ด Go ทั้งหมดไปยังโฟลเดอร์ทำงาน
COPY . .

# คำสั่งสร้าง binary ของแอปพลิเคชัน Go
RUN go build -o main .

EXPOSE 8080

# กำหนดคำสั่งที่จะรันเมื่อ Docker container ของคุณถูกเริ่มใช้งาน
CMD ["./main"]
