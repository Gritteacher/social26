ระบบเพิ่มข้อสอบเอง + นำเข้าไฟล์ + เปิด/ปิดข้อสอบรายชุด

เพิ่มใหม่ในเวอร์ชันนี้
1. admin.html มีระบบนำเข้าไฟล์คำถาม
   - รองรับ .csv
   - รองรับ .json
   - เลือกได้ว่าจะเพิ่มต่อจากข้อเดิม หรือแทนที่ข้อเดิมทั้งหมด

2. เปิด/ปิดข้อสอบแยกแต่ละชุด
   - ตารางรายการข้อสอบใน admin.html มีปุ่ม เปิด / ปิด แยกรายชุด

3. มีไฟล์ตัวอย่าง
   - template_import_questions.csv
   - template_import_questions.json

รูปแบบ CSV
question, choiceA, choiceB, choiceC, choiceD, choiceE, answer, explanation

ค่า answer ใส่ได้หลายแบบ
- ก ข ค ง จ
- A B C D E
- 1 2 3 4 5
- 0 1 2 3 4

ขั้นตอนอัปเดต
1. นำ Code.gs ไปวางทับใน Apps Script
2. Save
3. Deploy > Manage deployments > Edit
4. Version เลือก New version
5. Deploy
6. อัปโหลด index.html, quiz.html, admin.html ไปวางทับเว็บเดิม

Web App URL ที่ใส่ให้แล้ว:
https://script.google.com/macros/s/AKfycbxDoOUgSXVr0JFuGb6s6m4AnhVrH2U8xnIJZ-tkbQ_ddcDdtMy9Um0OPEQmzJMRK09V/exec

รหัสผ่านผู้ดูแลเริ่มต้น:
1234
