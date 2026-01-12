# Library Management System - Layered Architecture

## 📋 Project Information
- **Student Name:** [นายศุภโชค แสงจันทร์]
- **Student ID:** [67543210066-6]
- **Course:** ENGSE207 Software Architecture

## 🏗️ Architecture Style
Layered Architecture (3-tier)

## 📂 Project Structure
midterm-individual-67543210066-6/
├── src/
│ ├── presentation/
│ │ ├── routes/
│ │ │ └── bookRoutes.js
│ │ ├── controllers/
│ │ │ └── bookController.js
│ │ └── middlewares/
│ │ └── errorHandler.js
│ │
│ ├── business/
│ │ ├── services/
│ │ │ └── bookService.js
│ │ └── validators/
│ │ └── bookValidator.js
│ │
│ └── data/
│ ├── repositories/
│ │ └── bookRepository.js
│ └── database/
│ └── connection.js
│
├── public/
│ ├── css/
│ │ └── style.css
│ ├── js/
│ │ └── api.js
│ │ └── app.js
│ ├── index.html
├── server.js
├── package.json
├── package-lock.json
├── library.db
└── README.md


## 🎯 Refactoring Summary

### ปัญหาของ Monolithic (เดิม):
1. Code ยุ่งเหยิง - โค้ดทั้งหมดอยู่ในไฟล์เดียว (server.js) มากกว่า 400 บรรทัด
2. ยากต่อการบำรุงรักษา - แก้โค้ดส่วนหนึ่ง ต้องระวังไม่ให้กระทบส่วนอื่น
3. ทำงานร่วมกันยาก - Developer หลายคนแก้ไฟล์เดียวกัน เกิด conflict บ่อย
4. ไม่มี Separation of Concerns - Business logic ปนกับ Data access ปนกับ HTTP handling

### วิธีแก้ไขด้วย Layered Architecture:
1. แยก **Presentation Layer** (Controller/Routes/Middleware) → จัดการ HTTP request/response  
2. แยก **Business Layer** (Services/Validators) → จัดการ logic และ validation  
3. แยก **Data Layer** (Repository/Database) → จัดการ database operations  
4. ทำให้แต่ละ layer **ทำงานแยกกันได้** → maintain และ test ง่ายขึ้น  

### ประโยชน์ที่ได้รับ:
1. เพิ่มความ modular และ maintainable ของ code  
2. ง่ายต่อการเพิ่ม feature ใหม่โดยไม่กระทบ layer อื่น  
3. สามารถทดสอบแต่ละ layer ได้อย่างอิสระ  
4. ลดความซ้ำซ้อนของ database queries  
5. เพิ่มความเข้าใจ structure ของระบบสำหรับคนใหม่  

## 🚀 How to Run

```bash
# 1. Clone repository
git clone https://github.com/Jta003/midterm-individual-67543210066.git

# 2. Install dependencies
npm install

# 3. Run server
npm start

# 4. Test API
# Open browser: http://localhost:3000