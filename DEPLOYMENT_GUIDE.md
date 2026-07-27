# 📚 คู่มือการ Deploy บน GitHub Pages

## 🎯 เป้าหมาย

ทำให้ระบบจัดการคะแนน MBO สามารถเข้าถึงได้ผ่านเว็บ โดยใช้ GitHub Pages (ฟรี!)

---

## ✅ Step-by-Step Guide

### **ขั้นตอนที่ 1: สร้าง GitHub Account** (ถ้ายังไม่มี)

1. ไปที่ https://github.com/
2. คลิก "Sign up"
3. กรอกอีเมล, ชื่อผู้ใช้, และรหัสผ่าน
4. ยืนยันอีเมล

---

### **ขั้นตอนที่ 2: สร้าง Repository**

**ตัวเลือก A: Repository ชื่อพิเศษ (แนะนำ)**

```
ชื่อ: YOUR_USERNAME.github.io
Description: MBO Management System
Public: ✓ (ต้อง Public)
```

💡 **ข้อดี:** URL จะเป็น `https://YOUR_USERNAME.github.io` (สั้น)

**ตัวเลือก B: Repository ชื่อทั่วไป**

```
ชื่อ: mbo-system (หรือชื่ออื่นๆ)
Description: MBO Management System
Public: ✓
```

⚠️ **URL จะเป็น:** `https://YOUR_USERNAME.github.io/mbo-system/`

---

### **ขั้นตอนที่ 3: Upload ไฟล์**

#### **วิธีที่ 1: ใช้ Web Interface (ง่ายที่สุด)**

1. เปิด Repository ที่สร้างใหม่
2. คลิก "Add file" → "Upload files"
3. ลาก `index.html`, `README.md`, `.gitignore` มาที่โซน
4. คลิก "Commit changes"

#### **วิธีที่ 2: ใช้ Git Command (ถ้ามี Git ติดตั้ง)**

```bash
# โคลน Repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO

# คัดลอกไฟล์ (index.html, README.md, .gitignore)
# ไว้ในโฟลเดอร์นี้

# Add, Commit, Push
git add .
git commit -m "Initial commit: MBO System"
git push origin main
```

#### **วิธีที่ 3: ใช้ GitHub Desktop**

1. ติดตั้ง [GitHub Desktop](https://desktop.github.com/)
2. เปิด GitHub Desktop → "Clone a repository"
3. ค้นหา Repository ของคุณ → Clone
4. คัดลอกไฟล์เข้าโฟลเดอร์
5. สวิตช์ไปที่ GitHub Desktop → "Commit to main"
6. คลิก "Push origin"

---

### **ขั้นตอนที่ 4: เปิดใช้ GitHub Pages**

#### **สำหรับ Repository ชื่อ `YOUR_USERNAME.github.io`:**

✅ **GitHub Pages จะเปิดใช้งานอัตโนมัติ**

ให้เข้า: https://YOUR_USERNAME.github.io

#### **สำหรับ Repository ชื่อปกติ:**

1. เปิด Repository
2. ไปที่ **Settings** (ลูกศร ⚙️)
3. ค้นหา **"Pages"** ทางด้านซ้าย
4. ใต้ **"Source"** เลือก:
   - Branch: `main`
   - Folder: `/ (root)`
5. คลิก **"Save"**

✅ **รอ 1-2 นาที** จนกว่า GitHub จะ Deploy

---

### **ขั้นตอนที่ 5: ยืนยันว่าทำงาน**

1. เข้า URL: `https://YOUR_USERNAME.github.io` (หรือ `/mbo-system/`)
2. คุณควรเห็นหน้าแรกของระบบ MBO
3. ลองเลือกเดือน → สร้างเดือนใหม่ → ทำงานได้!

---

## 🔄 การอัพเดตไฟล์ในอนาคต

### **วิธีที่ 1: Web Interface**

1. เปิด Repository
2. คลิก ✏️ ที่ไฟล์ที่ต้องแก้ไข
3. แก้ไขเนื้อหา
4. คลิก "Commit changes"

### **วิธีที่ 2: Command Line**

```bash
cd YOUR_REPO
# แก้ไขไฟล์ตามต้องการ
git add .
git commit -m "Update: [อธิบายการเปลี่ยนแปลง]"
git push origin main
```

**GitHub Pages จะอัพเดตอัตโนมัติ!** ✨

---

## 🔐 การตั้งค่าเพิ่มเติม (Optional)

### **1. ตั้ง README เป็นหน้าแรกของ GitHub**

ไฟล์ `README.md` จะแสดงโดยอัตโนมัติด้านล่างรายการไฟล์

### **2. เพิ่ม .github/workflows (CI/CD)**

สร้างไฟล์ `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Deploy
        run: echo "Deployment successful"
```

---

## 🎨 การปรับแต่ง URL

### **ตั้งค่า Custom Domain (Optional)**

1. ซื้อ Domain (เช่น mbo-system.com)
2. ตั้งค่า DNS:
   - `A` record: `185.199.108.153`
   - `A` record: `185.199.109.153`
   - `A` record: `185.199.110.153`
   - `A` record: `185.199.111.153`
   - `CNAME` record: `YOUR_USERNAME.github.io`

3. Repository Settings → Pages → Custom domain
4. ใส่ `mbo-system.com`

---

## ❌ ปัญหาทั่วไปและวิธีแก้

### **ปัญหา: GitHub Pages ไม่ activate**

**วิธีแก้:**
1. ตรวจสอบว่า Repository เป็น **Public**
2. ไปที่ Settings → Pages → Branch ต้อง select `main`
3. รอ 5-10 นาที

### **ปัญหา: ไฟล์ไม่อัพเดท**

**วิธีแก้:**
1. Clear Browser Cache: `Ctrl + Shift + Delete`
2. Refresh หน้า: `Ctrl + F5` (Windows) หรือ `Cmd + Shift + R` (Mac)
3. ลองใช้ Incognito/Private Window

### **ปัญหา: 404 Error**

**วิธีแก้:**
1. ตรวจสอบว่า `index.html` อยู่ในโฟลเดอร์ root
2. ตรวจสอบ URL เป็น Case Sensitive
3. ตรวจสอบว่า Deploy เสร็จแล้ว (ดู Actions tab)

### **ปัญหา: ข้อมูล MBO หาย**

**วิธีแก้:**
- ข้อมูลเก็บใน Browser LocalStorage เท่านั้น
- ถ้า Clear Browser Data ข้อมูลจะหาย
- **ควร Export Excel เป็นประจำ!**

---

## 📊 ตรวจสอบสถานะ Deploy

### **ดู Actions (บันทึก Deploy)**

1. ไปที่ Repository
2. คลิก **"Actions"** tab
3. ดู Workflow runs
4. ถ้า ✅ = Deploy สำเร็จ
5. ถ้า ❌ = มีข้อผิดพลาด

---

## 🎓 เรียนรู้เพิ่มเติม

- [GitHub Pages Official Docs](https://docs.github.com/en/pages)
- [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
- [GitHub for Beginners](https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/)

---

## ✅ Checklist ก่อน Deploy

- [ ] สร้าง GitHub Account
- [ ] สร้าง Repository
- [ ] Upload `index.html`, `README.md`, `.gitignore`
- [ ] เปิดใช้ GitHub Pages
- [ ] รอ 1-2 นาท
- [ ] เข้า URL และทดสอบ
- [ ] ทำงานได้? ✅ สำเร็จ!

---

**สำเร็จ! ระบบของคุณอยู่บนอินเทอร์เน็ตแล้ว! 🎉**
