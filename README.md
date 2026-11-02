# HR Attendance

Ung dung cham cong, quan ly gio lam va xep lich lam viec theo kien truc modular monolith.

## Cau truc

- `be/`: Spring Boot 3.5, Java 21
- `fe/`: React 19 + TypeScript + Vite
- NeonDB hoac PostgreSQL duoc truyen qua bien moi truong backend

## Khoi dong PostgreSQL local

```powershell
docker compose up -d
```

## Chay backend

```powershell
cd be
.\mvnw.cmd spring-boot:run
```

API kiem tra suc khoe: `http://localhost:8080/api/v1/health`

## Chay frontend

```powershell
cd fe
Copy-Item .env.example .env.local
npm install
npm run dev
```

Frontend: `http://localhost:5173`

## Cau hinh NeonDB

Sao chep `be/.env.example`, dat gia tri Neon trong bien moi truong cua shell:

```powershell
$env:DB_URL="jdbc:postgresql://ep-example-pooler.region.aws.neon.tech/hr_attendance?sslmode=require"
$env:DB_USERNAME="your_neon_user"
$env:DB_PASSWORD="your_neon_password"
```

Khong commit thong tin ket noi, mat khau hoac chuoi ket noi cua NeonDB.
