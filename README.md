# 🚀 Personal Dashboard (Hub)

เว็บแอปพลิเคชันแดชบอร์ดส่วนตัว สำหรับรวมงาน จัดการตารางนัดหมาย และตั้งค่าระบบแจ้งเตือน รองรับการทำงานร่วมกับ Google Apps Script และ Google Sheets

## ✨ ฟีเจอร์หลัก
- **ระบบล็อกอิน:** ตรวจสอบสิทธิ์ผู้ใช้งานเบื้องต้นผ่าน Google Sheets
- **ปฏิทิน (FullCalendar):** รองรับมุมมองรายเดือน/สัปดาห์/วัน และปรับเปลี่ยนภาษาได้ (ไทย/อังกฤษ)
- **ระบบจัดการหมวดหมู่:** เพิ่มและกำหนดสีหมวดหมู่งานได้ตามต้องการ
- **ตั้งค่า LINE OA:** บันทึก Channel Access Token และ User ID สำหรับเชื่อมต่อการแจ้งเตือน

---

## 🛠️ วิธีการติดตั้งและใช้งาน

### 1. ตั้งค่า Backend (Google Apps Script)
1. สร้าง **Google Sheet** ใหม่ และสร้างชีตย่อย 3 ชีต ได้แก่:
   - `Users` (คอลัมน์: `username`, `password`, `role`)
   - `Events` (คอลัมน์: `timestamp`, `title`, `start`, `end`, `category`)
   - `Categories` (คอลัมน์: `name`, `color`)
2. ไปที่เมนู **ส่วนขยาย (Extensions)** > **Apps Script**
3. คัดลอกโค้ดจากไฟล์ `Code.gs` (ในโปรเจกต์นี้) ไปวางแทนที่ พร้อมใส่ Spreadsheet ID ของคุณในตัวแปร `SS_ID`
4. กด **Deploy** > **New deployment** 
   - เลือกประเภท: **Web app**
   - Execute as: **Me**
   - Who has access: **Anyone**
5. คัดลอก **Web App URL** ที่ได้เก็บไว้

### 2. ตั้งค่า Frontend (GitHub Pages)
1. นำไฟล์ `index.html` ไปไว้ใน Repository ของคุณ
2. เปิดไฟล์ `index.html` แล้วแทนที่ค่า `WEB_APP_URL` ด้วย URL ที่ได้จากขั้นตอน Google Apps Script
3. ไปที่การตั้งค่า Repository บน GitHub เลือก **Settings** > **Pages**
4. ตั้งค่า Build and deployment เป็น Branch `main` (หรือ `master`) และโฟลเดอร์ `/root` แล้วกด Save
5. รอสักครู่ จะได้ลิงก์เว็บไซต์ GitHub Pages สำหรับเข้าใช้งานแดชบอร์ดครับ
