# Persec 2026 — System Analyst Interview

คำตอบแบบทดสอบ System Analyst แยกไฟล์ตามสถานการณ์ เพื่อให้เปิดทีละข้อได้ตรง ๆ

ชื่อ repository ตอนอัปโหลดขึ้น GitHub ตามที่ข้อสอบกำหนด:

`persec2026-system-analyst-interview-<your-name>`

ส่ง URL กลับมาที่ `hr.team@persec.co.th`  
หัวข้ออีเมล: `[ชื่อ-นามสกุล] <ตำแหน่งที่สมัคร>`

## สารบัญ

| ไฟล์ | เรื่อง |
| --- | --- |
| [scenario-1-architecture.md](scenario-1-architecture.md) | สถานการณ์ที่ 1 ข้อ 1 — High-level architecture ของ Flash Sale 1,000 โค้ด / ผู้ใช้ 50,000 คนใน 5 นาที |
| [scenario-1-concurrency.md](scenario-1-concurrency.md) | สถานการณ์ที่ 1 ข้อ 2 — Logic กันกดซ้ำและกันแจกเกิน 1,000 สิทธิ์ |
| [scenario-2-mentoring.md](scenario-2-mentoring.md) | สถานการณ์ที่ 2 — ไกด์ Junior ให้ debug เอง โดยไม่แย่งคีย์บอร์ด |
| [scenario-3-coupon.md](scenario-3-coupon.md) | สถานการณ์ที่ 3 — คูปอง 100 สิทธิ์ คนกดพร้อมกันหลักหมื่นตอน 12:00 |
| [scenario-4-secrets.md](scenario-4-secrets.md) | สถานการณ์ที่ 4 — API key / URL ที่ถูก hardcode ในซอร์ส |
| [prompts.md](prompts.md) | Prompt ที่ใช้กับ AI ในแต่ละข้อ |

แต่ละไฟล์ขึ้นต้นด้วยคำตอบสั้น แล้วตามด้วยเหตุผล ตัวเลขที่ใช้กะขนาด และพฤติกรรมเมื่อชิ้นส่วนมีปัญหา

## สมมติฐานที่ใช้ร่วมกันในข้อสถาปัตยกรรม

- ผู้รับสิทธิ์ต้องล็อกอิน และ 1 บัญชีได้ 1 สิทธิ์ต่อแคมเปญ
- โค้ดหรือคูปองถูกสร้างไว้ในฐานข้อมูลครบจำนวนก่อนเวลาเปิด ไม่มีการสร้างเพิ่มตอนผู้ใช้กด
- Web กับ Mobile เรียก API ชุดเดียวกัน
- เวลา 12:00 น. คือ Asia/Bangkok และใช้เวลาของเซิร์ฟเวอร์เป็นตัวตัดสิน
