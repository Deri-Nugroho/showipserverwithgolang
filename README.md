# showipserverwithgolang
Script Go Lang sederhana untuk menampilkan alamat IP server (lokal/private) beserta port yang digunakan.

## Instal di AL23
```
yum install golang -y
```

## Build apps
```
go build -o showip-app main.go
```

## Testing
```
./showip-app
```

## Running in production
Use nodejs package manager
```
yum install nodejs -y
npm install -g pm2
pm2 start showip-app
```

# ☁️ Deploy ke AWS Elastic Beanstalk (Platform Go - Melalui VS Code) 
## 1. Inisialisasi modul Go (hanya sekali)
```
go mod init showip-app
```

## 2. Build Binary Linux (di lokal atau WSL)
```
GOOS=linux GOARCH=amd64 go build -o showip-app main.go
```

## ✅ Solusi Jika Menggunakan PowerShell
```
$env:GOOS="linux"
$env:GOARCH="amd64"
go build -o showip-app main.go
```

## 3. Buat file Procfile
```
web: ./showip-app
```

## 4. Buat file ZIP untuk deploy
```
zip deploy.zip showip-app Procfile
```

## 5. Upload deploy.zip ke AWS Elastic Beanstalk
