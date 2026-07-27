# 🎯 ระบบจัดการคะแนน MBO

ระบบจัดการคะแนน Management by Objectives (MBO) สำหรับบันทึกกิจกรรมและประเมินคะแนนพนักงาน รองรับการทำงานทั้งปี พ.ศ. 2567-2575

## ✨ ฟีเจอร์หลัก

- 📅 **ระบบรายเดือน** - แยกข้อมูลเป็นเดือน ทำงานแบบยืดหยุ่น
- 👥 **จัดการพนักงาน** - เพิ่ม/ลบพนักงาน พร้อมข้อมูลแผนกและกะการทำงาน
- 🙏 **กิจกรรม 1.1** - สวดมนต์ไหว้พระ กรวดน้ำ (อัพโหลดรูป + บันทึกวันที่)
- 🧹 **กิจกรรม 1.2** - กิจกรรม 9ส. & ทำความสะอาด (อัพโหลดรูป + บันทึกวันที่)
- ⭐ **กิจกรรม 2** - ประเมิน 9ส. 3 รอบ (คำนวณเฉลี่ยอัตโนมัติ)
- 📊 **แดชบอร์ด** - สรุปคะแนน อันดับพนักงาน สถิติต่างๆ
- 📥 **ส่งออกข้อมูล** - Export เป็นไฟล์ Excel รายเดือน หรือทั้งปี
- ✏️ **แก้ไข/ลบข้อมูล** - สามารถแก้ไขวันที่ และลบรายการได้

## 🚀 การใช้งาน (Local)

### ขั้นตอนที่ 1: Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/mbo-system.git
cd mbo-system
```

### ขั้นตอนที่ 2: เปิดไฟล์

1. **วิธีที่ 1 - ใช้ Live Server (Recommended)**
   - ติดตั้ง VS Code Extension "Live Server"
   - คลิกขวา `index.html` → "Open with Live Server"
   - เบราวเซอร์จะเปิดที่ `http://localhost:5500`

2. **วิธีที่ 2 - เปิดไฟล์โดยตรง**
   - ดับเบิลคลิก `index.html`
   - หรือลากไฟล์ไปที่เบราวเซอร์

### ขั้นตอนที่ 3: เริ่มใช้งาน

1. 🗓️ **เลือกเดือน/ปี** จากเมนู "เลือกเดือน/ปี"
2. ➕ **คลิก "สร้างเดือนใหม่"**
3. 📂 **คลิก "เปิดเดือน"**
4. เพิ่มข้อมูลตามต้องการ

## 📲 Deploy บน GitHub Pages

### วิธีที่ 1: ใช้ GitHub Desktop (ง่ายที่สุด)

```bash
1. Fork หรือสร้าง Repository ชื่อ: YOUR_USERNAME.github.io
2. Clone Repository ลงเครื่อง
3. วาง index.html ในโฟลเดอร์หลัก
4. Commit และ Push
5. เข้า https://YOUR_USERNAME.github.io/
```

### วิธีที่ 2: ใช้ Command Line

```bash
# สร้าง Repository ใหม่
git init
git add .
git commit -m "Initial commit: MBO System"
git remote add origin https://github.com/YOUR_USERNAME/mbo-system.git
git branch -M main
git push -u origin main

# ตั้งค่า GitHub Pages
# ไปที่ Settings → Pages → Source: main branch → Save
```

### วิธีที่ 3: Deploy ที่แอดเดรสที่กำหนด

```
https://YOUR_USERNAME.github.io/mbo-system/
```

**ขั้นตอน:**
1. สร้าง Repository `mbo-system`
2. Push ไฟล์ทั้งหมด
3. ตั้งค่า Settings → Pages → Source: main branch
4. รอ 1-2 นาที
5. เข้า URL ข้างบน

## 📊 โครงสร้างไฟล์

```
mbo-system/
├── index.html          # ไฟล์หลัก (HTML + CSS + JS)
├── README.md          # ไฟล์คำแนะนำ (ไฟล์นี้)
├── .gitignore         # ไฟล์ที่ไม่ต้อง push
└── assets/            # (Optional) โฟลเดอร์เก็บไฟล์ด้านนอก
    ├── styles.css     # (Optional) CSS แยก
    └── script.js      # (Optional) JavaScript แยก
```

## 💾 การเก็บข้อมูล

- **ทั้งหมดเก็บในเบราวเซอร์** (Browser LocalStorage)
- **ไม่มีเซิร์ฟเวอร์ส่วนกลาง** ข้อมูลส่วนตัว
- **แนะนำ**: Export เป็น Excel ทุกสัปดาห์เพื่อ Backup

## 🎯 เกณฑ์การให้คะแนน

### กิจกรรม 1.1 & 1.2
- การเข้าร่วม **95% ขึ้นไป** → **1 คะแนน**
- ต่ำกว่า 95% → **0 คะแนน**

### กิจกรรม 2 (เฉลี่ย 3 รอบ)
- **95%-100%** → **2 คะแนน** ✅
- **90%-94.99%** → **1 คะแนน** ⚠️
- **ต่ำกว่า 90%** → **0 คะแนน** ❌

### รวมคะแนน
- **5 คะแนน** = ดีเยี่ยม ⭐⭐⭐
- **3-4 คะแนน** = ปานกลาง ⭐⭐
- **ต่ำกว่า 3 คะแนน** = ต้องปรับปรุง ⭐

## 🛠️ การแก้ไขและปรับแต่ง

### เปลี่ยนชื่อแผนก

เปิด `index.html` แล้วค้นหา:
```html
<select id="employeeDept">
    <option value="แผนกคลังสินค้า">แผนกคลังสินค้า</option>
    <!-- เพิ่มหรือลบแผนกตามต้องการ -->
</select>
```

### เปลี่ยนสี Theme

ค้นหาในไฟล์:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

เปลี่ยน color codes ตามต้องการ

### เปลี่ยนปีเริ่มต้น

ค้นหา:
```javascript
const years = Array.from({length: 9}, (_, i) => 2567 + i);
```

เปลี่ยน `2567` และ `9` ตามต้องการ

## 🐛 Troubleshooting

### ปัญหา: ข้อมูลหายไปเมื่อปิดเบราวเซอร์

**คำตอบ:** Refresh หน้าเว็บ ข้อมูลควรจะอยู่ที่ LocalStorage

### ปัญหา: ไม่สามารถ Export Excel

**คำตอบ:** ตรวจสอบว่า popup blocker ไม่ได้ block ไฟล์ download

### ปัญหา: GitHub Pages ไม่อัพเดต

**คำตอบ:** 
1. Clear browser cache (Ctrl+Shift+Delete)
2. รอ 5-10 นาทีให้ GitHub update

## 📝 License

MIT License - สามารถใช้งานและปรับแต่งได้อย่างเสรี

## 👨‍💼 Author

สร้างขึ้นสำหรับ Management by Objectives (MBO) ของบริษัท

## 📞 Support

หากมีปัญหา:
1. ตรวจสอบ README นี้
2. ลองล้างข้อมูลเบราวเซอร์
3. ติดต่อผู้พัฒนา

---

**เวอร์ชั่น:** 1.0  
**อัพเดตล่าสุด:** กรกฎาคม 2567  
**สภาพ:** ✅ ใช้งานได้อย่างเต็มที่
