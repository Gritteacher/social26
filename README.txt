อัปเดต: แก้ไขชื่อแบบทดสอบได้

เพิ่มใน admin.html:
- ปุ่ม “แก้ไขชื่อ” ในตารางรายการข้อสอบ
- ฟอร์มแก้ไขชื่อแบบทดสอบ
- แก้ไขได้ 3 อย่าง:
  1. ชื่อข้อสอบ
  2. คำอธิบาย/หัวข้อย่อย
  3. ระดับชั้น

หมายเหตุ:
- ไม่ให้แก้รหัสข้อสอบ เพื่อไม่ให้ผลคะแนนเดิมและลิงก์ข้อสอบเดิมเสีย
- หลังวางไฟล์แล้ว ต้องนำ Code.gs ไปวางทับใน Apps Script แล้ว Deploy เป็น New version อีกครั้ง


อัปเดต:
- เอาปุ่มเข้า Dashboard ออกจากหน้า index.html แล้ว
- ยังเก็บไฟล์ dashboard.html ไว้เหมือนเดิม
- ครูยังเข้า Dashboard ได้โดยพิมพ์ URL ตรง เช่น /dashboard.html

เพิ่ม Dashboard รายห้อง

ไฟล์ใหม่:
- dashboard.html

สิ่งที่เพิ่ม:
1. หน้า dashboard.html สำหรับดูสรุปผลรายห้อง
   - เลือกห้อง ทุกห้อง / ม.6/1 - ม.6/12
   - แสดงจำนวนผู้ทำ
   - คะแนนเฉลี่ย
   - เปอร์เซ็นต์เฉลี่ย
   - อัตราผ่าน 50%
   - ตารางสรุปแยกห้อง
   - ตารางสรุปแยกชุดข้อสอบ
   - รายชื่อนักเรียนที่ส่งคำตอบ

2. index.html
   - เพิ่มปุ่ม “ดู Dashboard รายห้อง”

3. quiz.html
   - เปลี่ยนช่องห้องจากช่องพิมพ์ เป็น Dropdown ม.6/1 - ม.6/12

4. Code.gs
   - เพิ่ม action=dashboardSummary

สำคัญ:
หลังวางไฟล์แล้ว ให้นำ Code.gs ไปวางทับใน Apps Script และ Deploy เป็น New version อีกครั้ง

Web App URL:
https://script.google.com/macros/s/AKfycbxDoOUgSXVr0JFuGb6s6m4AnhVrH2U8xnIJZ-tkbQ_ddcDdtMy9Um0OPEQmzJMRK09V/exec


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
