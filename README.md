# KAN HUB — เว็บไซต์โกดังเสื้อผ้ามือสองญี่ปุ่น

เว็บ static (HTML/CSS/JS) สำหรับโชว์สินค้า → คลิกแอด LINE
Deploy บน Cloudflare Pages ผ่าน Git

## โครงสร้างไฟล์
- `index.html` และหน้าอื่น ๆ — แต่ละหน้าของเว็บ
- `styles.css` — สไตล์รวมทั้งเว็บ (แก้ที่เดียว ทุกหน้าเปลี่ยน)
- `shared.js` — สคริปต์รวม + **CONFIG กลาง** (เมนู, แผนที่, ปุ่ม LINE/โทร)

## ⚙️ แก้ข้อมูลติดต่อ (ที่เดียว)
เปิด `shared.js` แก้ตรง `var KAN = {...}` ด้านบนสุด:
- `lineUrl` — ลิงก์ LINE OA จริง
- `tel` — เบอร์โทรจริง (ไม่ต้องมีขีด)
- `telShow` — รูปแบบเบอร์ที่โชว์บนเว็บ

แก้เสร็จ ปุ่ม "แอด LINE" และ "โทร" ทั้งเว็บจะอัปเดตตามอัตโนมัติ

## Deploy ขึ้น Cloudflare Pages
1. push โค้ดขึ้น GitHub
2. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git
3. เลือก repo · Framework preset = None · Build command เว้นว่าง · Output = /
4. Save and Deploy → ได้ URL `xxx.pages.dev`

ทุกครั้งที่ `git push` Cloudflare จะ deploy ใหม่อัตโนมัติ
