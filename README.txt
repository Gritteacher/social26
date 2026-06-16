ตรวจและแก้ไขไฟล์แล้ว

จุดที่พบ:
1. admin.html มี JavaScript SyntaxError ในฟังก์ชัน deleteQuiz()
   สาเหตุคือข้อความ confirm มีการขึ้นบรรทัดใหม่จริงอยู่ในเครื่องหมายคำพูด "..."
   ทำให้สคริปต์ทั้งหน้าไม่ทำงาน และปุ่มโหลดข้อมูลข้อสอบใช้งานไม่ได้

สิ่งที่แก้:
- แก้ confirm ใน deleteQuiz() ให้ใช้ \n แทนการขึ้นบรรทัดใหม่จริง
- ตรวจ Syntax ของ JavaScript ใน admin.html, index.html, quiz.html แล้วผ่าน
- ตรวจ Syntax ของ Code.gs แล้วผ่าน
- คงระบบเดิมครบ: เพิ่มข้อสอบ, นำเข้า CSV/JSON, เปิด/ปิดรายชุด, ลบข้อสอบ

วิธีใช้งาน:
1. อัปโหลด index.html, quiz.html, admin.html ไปวางทับไฟล์เดิม
2. นำ Code.gs ไปวางทับใน Apps Script
3. กด Save
4. Deploy > Manage deployments > Edit
5. เลือก New version
6. กด Deploy

รหัสผ่านผู้ดูแลเริ่มต้น: 1234
