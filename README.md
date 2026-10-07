# แดชบอร์ดสถานการณ์ขยะประเทศไทย

เว็บ HTML/CSS/JavaScript แบบ static มี 2 แท็บ: ภาพรวมขยะ และการจัดการขยะ
ข้อมูลจริง 539 แถว (77 จังหวัด × ปี 2561–2567) อยู่ในตัวแปร `DATA` ภายใน data.js
ไม่อ่านไฟล์จากเครื่องเจ้าของ ไม่ต้องเชื่อม Google Drive ไม่ใช้ localhost ไม่ใช้ API หรือ CDN
ผู้เข้าชมได้รับหน้าเว็บและข้อมูลชุดเดียวกันจากเว็บที่ deploy แล้ว ไม่มีข้อมูลสดอัตโนมัติ

## ขึ้น GitHub Pages
1. สร้าง repository เช่น waste-dashboard
2. อัปโหลดไฟล์ **ภายในโฟลเดอร์นี้** ให้ index.html อยู่ระดับบนสุดของ repository ไม่อัปโหลดทั้ง ZIP
3. Commit ไปที่ main
4. เปิด Settings → Pages → Build and deployment
5. Source: Deploy from a branch → Branch: main → Folder: / (root) → Save
6. รอ deployment สำเร็จ แล้วเปิด URL ที่ GitHub แสดงในหน้า Pages
   รูปแบบทั่วไป: https://ชื่อบัญชี.github.io/waste-dashboard/

ไม่ต้องตั้ง Build command ไม่ต้องติดตั้ง Node/Python และไม่ต้องนำ notebook ขึ้นไปด้วย
คู่มือ: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## เปิดในเครื่อง
ดับเบิลคลิก index.html แล้วเปิดด้วย Chrome หรือ Edge ได้ทันที

## อัปเดตข้อมูล
ข้อมูลเป็น snapshot จาก notebook ที่แนบในโครงการ ต้องแก้อาร์เรย์ DATA ใน data.js และ commit ใหม่เพื่อเผยแพร่ข้อมูลชุดใหม่
ถ้าเพิ่มปี ต้องทบทวนข้อความช่วงปีในหน้าเว็บด้วย ค่าของตัวแปรปริมาณต้องเป็นตัวเลขและแต่ละคู่จังหวัด–ปีต้องไม่ซ้ำ

## ที่มาและความหมาย
- ข้อมูลที่ฝังใน Waste_Generated_Colab (2).ipynb และ 66002022_จังหวัดใดมีสัดส่วนขยะที่กำจัดไม่ถูกต้องสูงที่สุด_.ipynb
- ปี 2561 จาก data32_40_1.csv; ปี 2562–2567 จากชีต ขยะ รายจังหวัด ตาม notebook
- ตรวจค่าขยะเกิดขึ้นและกำจัดไม่ถูกต้องตรงกันครบ 539 คู่ก่อนรวมคอลัมน์ ไม่ต่อแถวซ้ำ
- generated_tpd / reused_tpd / correct_tpd / incorrect_tpd: ตัน/วัน
- residual_tonnes: ตัน ไม่บวกกับอัตรารายวัน
- สัดส่วนรวม = ผลรวมขยะกำจัดไม่ถูกต้อง / ผลรวมขยะเกิดขึ้น × 100
- การ์ดและแนวโน้มเปลี่ยนตามจังหวัด กราฟอันดับและการกระจายยังแสดงทั้งประเทศ มีคำอธิบายบนหน้า
- เป็น Descriptive Analytics ไม่มีโมเดลทำนาย ไม่ปรับค่าผิดสังเกตต้นทางอัตโนมัติ

ข้อมูลที่ฝังในเว็บสามารถดาวน์โหลดได้โดยผู้ที่เข้าถึงเว็บ ไม่มีรหัสผ่านหรือข้อมูลเชื่อมต่อส่วนตัวในชุดไฟล์นี้

ต้องอัปโหลด index.html, data.js และ app.js ไว้โฟลเดอร์เดียวกัน โครงสร้าง HTML ระบุ head/body ชัดเจน รองรับ Live Server
