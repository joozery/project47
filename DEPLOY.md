# 🚀 Deploy to Netlify

## 📋 ขั้นตอนการ Deploy

### 1. Build Project
```bash
npm run build
```

### 2. Deploy Methods

#### Method 1: Drag & Drop (ง่ายที่สุด)
1. ไปที่ [netlify.com](https://netlify.com)
2. สมัครสมาชิกหรือเข้าสู่ระบบ
3. ลากโฟลเดอร์ `dist` ไปวางในพื้นที่ "Drag and drop your site output folder here"
4. รอสักครู่ Netlify จะ deploy ให้อัตโนมัติ
5. ได้ URL สำหรับเว็บไซต์

#### Method 2: Git Integration (แนะนำสำหรับการอัพเดท)
1. Push โค้ดไปยัง GitHub/GitLab
2. เชื่อมต่อ repository กับ Netlify
3. ตั้งค่า build command: `npm run build`
4. ตั้งค่า publish directory: `dist`
5. Netlify จะ auto-deploy ทุกครั้งที่ push code

#### Method 3: Netlify CLI
```bash
# ติดตั้ง Netlify CLI
npm install -g netlify-cli

# Login
netlify login

# Deploy
netlify deploy --prod --dir=dist
```

## ⚙️ การตั้งค่า

### Build Settings
- **Build command**: `npm run build`
- **Publish directory**: `dist`
- **Node version**: 20+

### Environment Variables (ถ้าจำเป็น)
- `VITE_API_URL`: URL ของ API
- `VITE_APP_NAME`: ชื่อแอป

## 🔧 การแก้ไขปัญหา

### 404 Error
- ตรวจสอบไฟล์ `_redirects` ในโฟลเดอร์ `dist`
- ตรวจสอบการตั้งค่า redirects ใน Netlify

### Build Error
- ตรวจสอบ Node.js version (ต้องเป็น 20.19+ หรือ 22.12+)
- ตรวจสอบ dependencies ใน `package.json`

## 📱 การทดสอบ
1. เปิดเว็บไซต์ที่ได้จาก Netlify
2. ทดสอบฟีเจอร์หลัก:
   - การแสดงผลหน้าแรก
   - การเปิดรายงาน
   - การกรอกข้อมูลฟอร์ม
   - การกด Start/Stop Timer
   - การแสดงกราฟ
   - การพิมพ์

## 🎯 หมายเหตุ
- ไฟล์ `_redirects` และ `netlify.toml` ถูกสร้างไว้แล้ว
- กราฟจะทำงานแบบ client-side (ไม่ต้องการ server)
- ข้อมูลจะถูกเก็บใน localStorage ของเบราว์เซอร์
