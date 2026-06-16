ระบบใหม่: ครูเพิ่มข้อสอบเองได้

ไฟล์ในชุดนี้
1. index.html
   - แสดงการ์ดข้อสอบทั้งหมดจาก Google Sheet
   - แสดงเฉพาะข้อสอบที่เปิดอยู่

2. quiz.html
   - รับ quizId จาก URL เช่น quiz.html?quizId=economics-basic
   - โหลดคำถามจาก Google Sheet
   - นักเรียนไม่เห็นคะแนนและเฉลย

3. admin.html
   - สร้างชุดข้อสอบใหม่
   - เพิ่มคำถามเอง
   - เปิด/ปิดแต่ละชุดข้อสอบ
   - รหัสผ่านเริ่มต้น: 1234

4. Code.gs
   - Backend ทั้งหมด
   - สร้าง Google Sheet อัตโนมัติ
   - Seed ข้อสอบเศรษฐศาสตร์เดิมให้อัตโนมัติครั้งแรก
   - ส่งอีเมลผลสอบให้ครู

ขั้นตอนใช้งาน
1. นำ Code.gs ไปวางทับใน Apps Script
2. Save
3. Deploy > Manage deployments > Edit
4. Version เลือก New version
5. Deploy
6. อัปโหลด index.html, quiz.html, admin.html ไปวางทับเว็บเดิม

Web App URL ที่ใส่ให้แล้ว:
https://script.google.com/macros/s/AKfycbxDoOUgSXVr0JFuGb6s6m4AnhVrH2U8xnIJZ-tkbQ_ddcDdtMy9Um0OPEQmzJMRK09V/exec

หมายเหตุ
- หากต้องการเปลี่ยนรหัสผ่านครู ให้แก้ใน Code.gs:
  const ADMIN_KEY = "1234";
