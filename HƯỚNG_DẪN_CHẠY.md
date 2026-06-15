# 🚀 Hướng dẫn Chạy Dự án (React Frontend + NestJS Backend)

## ⚡ Bước 1: Chuẩn bị môi trường

### Yêu cầu
- **Node.js**: v18+ (https://nodejs.org/)
- **npm** hoặc **yarn**: Cài kèm Node.js
- **Git**: Để clone repo

### Kiểm tra cài đặt
```bash
node --version    # v18.x.x
npm --version     # 9.x.x
```

---

## 📦 Bước 2: Cài đặt Backend (NestJS)

### 2.1 Vào thư mục backend
```bash
cd backend
```

### 2.2 Cài đặt dependencies
```bash
npm install
```

### 2.3 Cấu hình Database (Prisma)
```bash
# Tạo file schema từ Prisma
npm run prisma:generate

# Push schema lên database
npm run prisma:push

# (Optional) Xem database UI
npm run prisma:studio
```

### 2.4 Chạy Backend
```bash
# Development mode (auto-reload)
npm run start:dev

# Production mode
npm run start:prod
```

✅ Backend chạy tại: **http://localhost:3000**

---

## 🎨 Bước 3: Cài đặt Frontend (React)

### 3.1 Vào thư mục frontend (terminal mới)
```bash
cd frontend
```

### 3.2 Cài đặt dependencies
```bash
npm install
```

### 3.3 Cấu hình Environment
Kiểm tra file `.env` có nội dung:
```
REACT_APP_API_URL=http://localhost:3000
```

Nếu chưa có, tạo file `.env`:
```bash
echo "REACT_APP_API_URL=http://localhost:3000" > .env
```

### 3.4 Chạy Frontend
```bash
npm start
```

✅ Frontend mở tại: **http://localhost:3000** (React app sẽ chạy trên port 3001 hoặc 3002)

---

## ✅ Kiểm tra Hệ thống

Sau khi cả Frontend và Backend chạy:

### 1. Backend API
Truy cập: http://localhost:3000
- Nếu thấy text "Hello World" → Backend ✅

### 2. Frontend
- Trang chủ (Home): http://localhost:3001 hoặc port khác
- Tìm kiếm phòng: Gõ các filter và nhấn "Tìm kiếm"
- Đăng ký: `/register`
- Đăng nhập: `/login`

### 3. Network Tab (F12)
- Mở DevTools (F12)
- Vào tab Network
- Refresh trang
- Kiểm tra request tới `/rooms` hay `/auth` → có response từ backend?

---

## 🔧 Các Lệnh Hữu Ích

### Backend
```bash
# Development server
npm run start:dev

# Build production
npm run build

# Chạy tests
npm run test

# Tạo migration từ schema
npm run prisma:generate

# Xem database
npm run prisma:studio
```

### Frontend
```bash
# Development server
npm start

# Build production
npm run build

# Chạy tests
npm test

# Eject (không nên dùng)
npm run eject
```

---

## 📝 Các tính năng có sẵn

### ✅ Người thuê (Role: 1)
- [x] Xem danh sách phòng
- [x] Tìm kiếm & lọc phòng (giá, diện tích, vị trí)
- [x] Xem chi tiết phòng + ảnh slider
- [x] Xem thông tin liên hệ chủ trọ

### ✅ Chủ trọ (Role: 2)
- [x] Đăng tin phòng mới
- [x] Upload hình ảnh
- [x] Chọn tiện ích
- [x] Dashboard: xem danh sách phòng
- [x] Sửa/Xóa/Đổi trạng thái phòng

### ✅ Admin (Role: 3)
- [x] Quản lý loại phòng
- [x] Quản lý tiện ích
- [x] Quản lý người dùng

---

## 🐛 Troubleshooting

### ❌ Error: "Cannot find module 'react'"
**Solution**: Chạy `npm install` trong thư mục frontend

### ❌ Error: CORS blocked
**Solution**: Backend đã có `app.enableCors()`, kiểm tra lại

### ❌ Error: "localhost:3000 refused to connect"
**Solution**: Backend chưa chạy, chạy `npm run start:dev` trong backend

### ❌ Error: "Unexpected token" khi build
**Solution**: Xóa folder `node_modules` và `package-lock.json`, rồi chạy `npm install` lại

### ❌ Database connection error
**Solution**: Kiểm tra Prisma schema và chạy `npm run prisma:push`

---

## 💡 Tips

1. **Sử dụng 2 Terminal**: Một cho Backend, một cho Frontend
2. **DevTools**: Dùng F12 để kiểm tra console, network requests
3. **LocalStorage**: Token được lưu, F12 → Application → LocalStorage → check `token` và `user`
4. **Validation**: Tất cả validation được làm trên Frontend đầu tiên

---

## 📚 Tài liệu Thêm

- [React Docs](https://react.dev)
- [NestJS Docs](https://docs.nestjs.com)
- [Prisma Docs](https://www.prisma.io/docs)
- [Axios Docs](https://axios-http.com)

---

**Chúc bạn code vui vẻ! 🚀**
