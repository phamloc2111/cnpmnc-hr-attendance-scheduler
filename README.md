# HR Attendance

An attendance, working-hours management, and work-scheduling application built with a modular monolith architecture.

## Project Structure

- `be/`: Spring Boot 3.5 and Java 21
- `fe/`: React 19 + TypeScript + Vite
- `mobile/`: Flutter application for Android and iOS
- NeonDB or PostgreSQL connection configured through backend environment variables

## Start Local PostgreSQL

```powershell
docker compose up -d
```

## Run the Backend

```powershell
cd be
.\mvnw.cmd spring-boot:run
```

Health check API: `http://localhost:8080/api/v1/health`

## Run the Frontend

```powershell
cd fe
Copy-Item .env.example .env.local
npm install
npm run dev
```

Frontend: `http://localhost:5173`

## Run the Mobile Application

```powershell
cd mobile
flutter pub get
flutter run
```

## Configure NeonDB

Copy `be/.env.example` to `be/.env`, then set your NeonDB values:

```dotenv
DB_URL=jdbc:postgresql://ep-example-pooler.region.aws.neon.tech/hr_attendance?sslmode=require
DB_USERNAME=your_neon_user
DB_PASSWORD=your_neon_password
```

Alternatively, set them as shell environment variables in PowerShell:

```powershell
$env:DB_URL="jdbc:postgresql://ep-example-pooler.region.aws.neon.tech/hr_attendance?sslmode=require"
$env:DB_USERNAME="your_neon_user"
$env:DB_PASSWORD="your_neon_password"
```

Do not commit NeonDB connection details, passwords, or connection strings.
