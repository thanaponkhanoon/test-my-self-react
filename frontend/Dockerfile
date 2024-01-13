# เลือกเวอร์ชันของ Node.js ที่คุณต้องการใช้
FROM node:14

# กำหนดพื้นที่ที่จะใช้ใน container
WORKDIR /app

# คัดลอก package.json และ package-lock.json (หากมี) เพื่อให้รัน npm install เร็วขึ้น
COPY package*.json ./

# ติดตั้ง dependencies
RUN npm install

# คัดลอกโค้ดของ React application ไปยัง container
COPY . .

# สร้าง build ของ React application
RUN npm run build

# กำหนด port ที่จะเปิดให้เข้าถึง React application
EXPOSE 3000

# คำสั่งที่จะรันเมื่อ container เริ่มต้น
CMD ["npm", "start"]
