# i-Store Back Office Web — Netlify Ready

โปรเจกต์นี้เป็น React + Vite และเตรียม Netlify Functions สำหรับ `/api/ai` เรียบร้อยแล้ว

## Deploy ไป Netlify

1. อัปโหลดโฟลเดอร์นี้ขึ้น GitHub (แนะนำ) หรือเชื่อม repository กับ Netlify
2. ใน Netlify เลือก **Add new project → Import an existing project**
3. Build command: `npm run build`
4. Publish directory: `dist`
5. Functions directory: `netlify/functions` (มีระบุไว้ใน `netlify.toml` แล้ว)
6. ตั้ง Environment Variable ชื่อ `ANTHROPIC_API_KEY` ใน Netlify
7. Deploy

> ห้ามใส่ API key ลงในไฟล์ frontend หรือ commit `.env` ขึ้น GitHub

## Local development

- UI: `npm run dev`
- Build test: `npm run build`
- ถ้าต้องการทดสอบ Netlify Function ในเครื่อง แนะนำใช้ Netlify CLI: `netlify dev`

## หมายเหตุ

- ข้อมูลที่เก็บผ่าน `localStorage` จะอยู่เฉพาะ browser/เครื่องนั้น ไม่ได้แชร์กับพนักงานคนอื่น
- AI เรียกผ่าน Netlify Function เพื่อไม่เปิดเผย Anthropic API key ใน browser
