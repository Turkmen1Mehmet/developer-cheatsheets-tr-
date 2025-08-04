# Docker Cheatsheet - Kapsamlı Docker Referans Rehberi

Bu rehber Docker'ın temel ve ileri seviye konularını kapsar. Her komutun Türkçe açıklaması bulunmaktadır.

## İçindekiler

1. [Docker Kurulumu ve Yapılandırma](#1-docker-kurulumu-ve-yapılandırma)
2. [Temel Docker Komutları](#2-temel-docker-komutları)
3. [Image İşlemleri](#3-image-işlemleri)
4. [Container İşlemleri](#4-container-işlemleri)
5. [Dockerfile](#5-dockerfile)
6. [Docker Compose](#6-docker-compose)
7. [Volume ve Bind Mount](#7-volume-ve-bind-mount)
8. [Network İşlemleri](#8-network-işlemleri)
9. [Registry İşlemleri](#9-registry-işlemleri)
10. [Multi-stage Builds](#10-multi-stage-builds)
11. [Docker Swarm](#11-docker-swarm)
12. [Güvenlik](#12-güvenlik)
13. [Monitoring ve Logging](#13-monitoring-ve-logging)
14. [Optimizasyon](#14-optimizasyon)
15. [Troubleshooting](#15-troubleshooting)
16. [Best Practices](#16-best-practices)
17. [CI/CD Entegrasyonu](#17-cicd-entegrasyonu)
18. [Cloud Platformları](#18-cloud-platformları)
19. [Container Orchestration](#19-container-orchestration)
20. [Advanced Docker Features](#20-advanced-docker-features)
21. [Docker Desktop](#21-docker-desktop)
22. [Docker Buildx](#22-docker-buildx)
23. [Docker Scan](#23-docker-scan)
24. [Docker Trust](#24-docker-trust)
25. [Docker Content Trust](#25-docker-content-trust)
26. [Docker Secrets](#26-docker-secrets)
27. [Docker Configs](#27-docker-configs)
28. [Docker Events](#28-docker-events)
29. [Docker System](#29-docker-system)
30. [Docker Context](#30-docker-context)
31. [Docker Plugin](#31-docker-plugin)
32. [Docker Extension](#32-docker-extension)
33. [Docker Scout](#33-docker-scout)
34. [Docker Dev Environments](#34-docker-dev-environments)
35. [Docker Compose V2](#35-docker-compose-v2)
36. [Docker Compose Profiles](#36-docker-compose-profiles)
37. [Docker Compose Override](#37-docker-compose-override)
38. [Docker Compose Extensions](#38-docker-compose-extensions)
39. [Docker Compose Watch](#39-docker-compose-watch)
40. [Docker Compose Build](#40-docker-compose-build)
41. [Docker Compose Deploy](#41-docker-compose-deploy)
42. [Docker Compose Config](#42-docker-compose-config)
43. [Docker Compose Convert](#43-docker-compose-convert)
44. [Docker Compose Pull](#44-docker-compose-pull)
45. [Docker Compose Push](#45-docker-compose-push)
46. [Docker Compose Scale](#46-docker-compose-scale)
47. [Docker Compose Top](#47-docker-compose-top)
48. [Docker Compose Pause](#48-docker-compose-pause)
49. [Docker Compose Unpause](#49-docker-compose-unpause)
50. [Docker Compose Kill](#50-docker-compose-kill)
51. [Docker Compose Exec](#51-docker-compose-exec)
52. [Docker Compose Run](#52-docker-compose-run)
53. [Docker Compose Port](#53-docker-compose-port)
54. [Docker Compose Images](#54-docker-compose-images)
55. [Docker Compose Volumes](#55-docker-compose-volumes)
56. [Docker Compose Networks](#56-docker-compose-networks)
57. [Docker Compose Configs](#57-docker-compose-configs)
58. [Docker Compose Secrets](#58-docker-compose-secrets)
59. [Docker Compose Healthcheck](#59-docker-compose-healthcheck)
60. [Docker Compose Depends On](#60-docker-compose-depends-on)
61. [Docker Compose Environment](#61-docker-compose-environment)
62. [Docker Compose Env File](#62-docker-compose-env-file)
63. [Docker Compose Labels](#63-docker-compose-labels)
64. [Docker Compose Annotations](#64-docker-compose-annotations)
65. [Docker Compose Deploy](#65-docker-compose-deploy)
66. [Docker Compose Resources](#66-docker-compose-resources)
67. [Docker Compose Restart Policy](#67-docker-compose-restart-policy)
68. [Docker Compose Update Config](#68-docker-compose-update-config)
69. [Docker Compose Rollback Config](#69-docker-compose-rollback-config)
70. [Docker Compose Placement](#70-docker-compose-placement)
71. [Docker Compose Constraints](#71-docker-compose-constraints)
72. [Docker Compose Preferences](#72-docker-compose-preferences)
73. [Docker Compose Replicas](#73-docker-compose-replicas)
74. [Docker Compose Endpoint Mode](#74-docker-compose-endpoint-mode)
75. [Docker Compose Ports](#75-docker-compose-ports)
76. [Docker Compose Expose](#76-docker-compose-expose)
77. [Docker Compose Links](#77-docker-compose-links)
78. [Docker Compose External Links](#78-docker-compose-external-links)
79. [Docker Compose Extra Hosts](#79-docker-compose-extra-hosts)
80. [Docker Compose DNS](#80-docker-compose-dns)
81. [Docker Compose DNS Search](#81-docker-compose-dns-search)
82. [Docker Compose DNS Options](#82-docker-compose-dns-options)
83. [Docker Compose Hostname](#83-docker-compose-hostname)
84. [Docker Compose Domainname](#84-docker-compose-domainname)
85. [Docker Compose Mac Address](#85-docker-compose-mac-address)
86. [Docker Compose Init](#86-docker-compose-init)
87. [Docker Compose Tty](#87-docker-compose-tty)
88. [Docker Compose Stdin Open](#88-docker-compose-stdin-open)
89. [Docker Compose Working Dir](#89-docker-compose-working-dir)
90. [Docker Compose User](#90-docker-compose-user)
91. [Docker Compose Group Add](#91-docker-compose-group-add)
92. [Docker Compose Cap Add](#92-docker-compose-cap-add)
93. [Docker Compose Cap Drop](#93-docker-compose-cap-drop)
94. [Docker Compose Security Opt](#94-docker-compose-security-opt)
95. [Docker Compose Read Only](#95-docker-compose-read-only)
96. [Docker Compose Tmpfs](#96-docker-compose-tmpfs)
97. [Docker Compose Sysctls](#97-docker-compose-sysctls)
98. [Docker Compose Ulimits](#98-docker-compose-ulimits)
99. [Docker Compose Logging](#99-docker-compose-logging)
100. [Docker Compose Log Driver](#100-docker-compose-log-driver)

---

## 1. Docker Kurulumu ve Yapılandırma

**Ne İşe Yarar:** Docker'ı farklı işletim sistemlerinde nasıl kuracağınızı ve yapılandıracağınızı öğretir. Kurulum sonrası temel ayarları ve güvenlik yapılandırmalarını kapsar.

**Ne Yapar:** Docker'ı sisteminize kurar, servis olarak başlatır ve temel yapılandırma ayarlarını yapar. Farklı işletim sistemleri için özel kurulum adımlarını gösterir.

### Docker Kurulumu (Ubuntu/Debian)
```bash
# Gerekli paketleri yükle
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release

# Docker'ın GPG anahtarını ekle
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Docker repository'sini ekle
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Docker'ı yükle
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io

# Kullanıcıyı docker grubuna ekle
sudo usermod -aG docker $USER
```

### Docker Kurulumu (macOS)
```bash
# Homebrew ile kurulum
brew install --cask docker

# Veya Docker Desktop'ı manuel olarak indir
# https://www.docker.com/products/docker-desktop
```

### Docker Kurulumu (Windows)
```powershell
# Chocolatey ile kurulum
choco install docker-desktop

# Veya Docker Desktop'ı manuel olarak indir
# https://www.docker.com/products/docker-desktop
```

### Docker Servisini Başlatma
```bash
# Docker servisini başlat
sudo systemctl start docker

# Sistem başlangıcında otomatik başlat
sudo systemctl enable docker

# Docker durumunu kontrol et
sudo systemctl status docker
```

### Docker Yapılandırması
```bash
# Docker daemon yapılandırması
sudo nano /etc/docker/daemon.json

# Örnek yapılandırma
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  },
  "storage-driver": "overlay2",
  "insecure-registries": ["localhost:5000"]
}
```

---

## 2. Temel Docker Komutları

**Ne İşe Yarar:** Docker ile çalışırken en sık kullanılan temel komutları öğretir. Docker'ın durumunu kontrol etme, sistem bilgilerini görüntüleme ve yardım alma gibi işlemleri kapsar.

**Ne Yapar:** Docker'ın kurulu olup olmadığını kontrol eder, versiyon bilgilerini gösterir, sistem kaynaklarının kullanımını izler ve Docker ile ilgili yardım bilgilerini sağlar.

### Docker Versiyon Kontrolü
```bash
# Docker versiyonunu göster
docker --version
docker version

# Docker info
docker info
```

### Docker Sistem Bilgileri
```bash
# Sistem kullanımını göster
docker system df

# Disk kullanımını detaylı göster
docker system df -v

# Kullanılmayan kaynakları temizle
docker system prune

# Tüm kullanılmayan kaynakları temizle (dikkatli kullanın!)
docker system prune -a
```

### Docker Yardım
```bash
# Genel yardım
docker --help

# Komut yardımı
docker run --help
docker build --help
```

---

## 3. Image İşlemleri

**Ne İşe Yarar:** Docker image'larını yönetmek için gerekli tüm komutları öğretir. Image'ları indirme, oluşturma, etiketleme, inceleme ve silme işlemlerini kapsar.

**Ne Yapar:** Docker image'larını registry'lerden indirir, Dockerfile'lardan yeni image'lar oluşturur, image'lara etiket ekler, image detaylarını inceler ve gereksiz image'ları temizler.

### Image Listeleme
```bash
# Yerel image'ları listele
docker images
docker image ls

# Tüm image'ları listele (dangling image'lar dahil)
docker images -a

# Image'ları formatlı göster
docker images --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}\t{{.CreatedAt}}"
```

### Image İndirme
```bash
# Image indir
docker pull ubuntu:latest
docker pull nginx:alpine
docker pull python:3.9-slim

# Belirli bir tag'i indir
docker pull ubuntu:20.04

# Private registry'den indir
docker pull registry.example.com/myapp:v1.0
```

### Image Oluşturma
```bash
# Dockerfile'dan image oluştur
docker build -t myapp:latest .

# Belirli bir Dockerfile kullan
docker build -f Dockerfile.prod -t myapp:prod .

# Build context'i belirt
docker build -t myapp:latest /path/to/context

# Build argümanları ile
docker build --build-arg VERSION=1.0 -t myapp:latest .
```

### Image Etiketleme
```bash
# Image'a tag ekle
docker tag myapp:latest myapp:v1.0

# Registry'ye push için etiketle
docker tag myapp:latest registry.example.com/myapp:latest
```

### Image Push/Pull
```bash
# Image'ı registry'ye push et
docker push myapp:latest
docker push registry.example.com/myapp:latest

# Private registry'den pull
docker pull registry.example.com/myapp:latest

# Login ol
docker login registry.example.com
```

### Image İnceleme
```bash
# Image detaylarını göster
docker image inspect ubuntu:latest

# Image geçmişini göster
docker history ubuntu:latest

# Image içeriğini incele
docker run --rm -it ubuntu:latest ls -la
```

### Image Silme
```bash
# Image sil
docker rmi ubuntu:latest
docker image rm ubuntu:latest

# Kullanılmayan image'ları sil
docker image prune

# Tüm image'ları sil (dikkatli kullanın!)
docker image prune -a
```

---

## 4. Container İşlemleri

**Ne İşe Yarar:** Docker container'larını yönetmek için gerekli tüm komutları öğretir. Container'ları çalıştırma, durdurma, başlatma, silme ve içine girme işlemlerini kapsar.

**Ne Yapar:** Image'lardan container'lar oluşturur, çalışan container'ları yönetir, container loglarını görüntüler, container'lara bağlanır ve container durumlarını izler.

### Container Çalıştırma
```bash
# Container'ı çalıştır
docker run ubuntu:latest

# Interactive mode ile çalıştır
docker run -it ubuntu:latest /bin/bash

# Detached mode ile çalıştır
docker run -d nginx:alpine

# Port mapping ile çalıştır
docker run -p 8080:80 nginx:alpine

# Volume mount ile çalıştır
docker run -v /host/path:/container/path ubuntu:latest

# Environment variable ile çalıştır
docker run -e VAR_NAME=value ubuntu:latest

# Container adı belirt
docker run --name my-container ubuntu:latest

# Network belirt
docker run --network my-network ubuntu:latest
```

### Container Listeleme
```bash
# Çalışan container'ları listele
docker ps

# Tüm container'ları listele
docker ps -a

# Container'ları formatlı göster
docker ps --format "table {{.Names}}\t{{.Image}}\t{{.Status}}\t{{.Ports}}"

# Son N container'ı göster
docker ps -n 5
```

### Container Durumu
```bash
# Container durumunu kontrol et
docker ps -q | xargs docker inspect --format='{{.State.Status}}'

# Container loglarını göster
docker logs container_name

# Canlı log takibi
docker logs -f container_name

# Son N satır log
docker logs --tail 100 container_name
```

### Container Durdurma/Başlatma
```bash
# Container'ı durdur
docker stop container_name

# Container'ı başlat
docker start container_name

# Container'ı yeniden başlat
docker restart container_name

# Container'ı duraklat
docker pause container_name

# Container'ı devam ettir
docker unpause container_name
```

### Container İçine Girme
```bash
# Container'a bash ile bağlan
docker exec -it container_name /bin/bash

# Container'a sh ile bağlan
docker exec -it container_name /bin/sh

# Belirli bir kullanıcı ile bağlan
docker exec -it -u root container_name /bin/bash

# Belirli bir komut çalıştır
docker exec container_name ls -la
```

### Container Silme
```bash
# Container sil
docker rm container_name

# Çalışan container'ı zorla sil
docker rm -f container_name

# Tüm durmuş container'ları sil
docker container prune

# Tüm container'ları sil (dikkatli kullanın!)
docker rm $(docker ps -aq)
```

### Container İnceleme
```bash
# Container detaylarını göster
docker inspect container_name

# Container IP adresini al
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name

# Container port mapping'ini göster
docker port container_name

# Container resource kullanımını göster
docker stats container_name
```

---

## 5. Dockerfile

**Ne İşe Yarar:** Docker image'ları oluşturmak için kullanılan Dockerfile dosyalarının nasıl yazılacağını öğretir. Image oluşturma sürecini otomatikleştirmek için gerekli talimatları kapsar.

**Ne Yapar:** Uygulamanızı container'a paketlemek için gerekli adımları tanımlar, bağımlılıkları yükler, dosyaları kopyalar, port'ları açar ve çalıştırma komutlarını belirler.

### Temel Dockerfile Yapısı
```dockerfile
# Base image
FROM ubuntu:20.04

# Metadata
LABEL maintainer="your-email@example.com"
LABEL version="1.0"
LABEL description="My application"

# Environment variables
ENV NODE_ENV=production
ENV PORT=3000

# Working directory
WORKDIR /app

# Copy files
COPY package*.json ./
COPY . .

# Install dependencies
RUN apt-get update && apt-get install -y \
    nodejs \
    npm \
    && rm -rf /var/lib/apt/lists/*

RUN npm install

# Expose port
EXPOSE 3000

# Health check
HEALTHCHECK --interval=30s --timeout=3s \
  CMD curl -f http://localhost:3000/health || exit 1

# Default command
CMD ["npm", "start"]
```

### Multi-stage Build
```dockerfile
# Build stage
FROM node:16 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

# Production stage
FROM node:16-alpine
WORKDIR /app
COPY --from=builder /app/node_modules ./node_modules
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

### Optimizasyon Teknikleri
```dockerfile
# Layer cache'leme
FROM ubuntu:20.04
WORKDIR /app

# Dependencies'i önce kopyala (cache için)
COPY requirements.txt .
RUN pip install -r requirements.txt

# Sonra uygulama kodunu kopyala
COPY . .

# .dockerignore kullan
# node_modules
# .git
# .env
# *.log
```

### Build Argümanları
```dockerfile
ARG VERSION=latest
ARG BUILD_DATE
ARG VCS_REF

FROM ubuntu:20.04

LABEL org.label-schema.version=$VERSION \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.vcs-ref=$VCS_REF

# Build time'da kullan
RUN echo "Building version $VERSION"
```

---

## 6. Docker Compose

**Ne İşe Yarar:** Birden fazla container'dan oluşan uygulamaları tanımlamak ve yönetmek için kullanılan Docker Compose'u öğretir. Multi-container uygulamaların nasıl oluşturulacağını kapsar.

**Ne Yapar:** Birden fazla servisi tek bir dosyada tanımlar, servisler arası bağımlılıkları yönetir, network ve volume'ları otomatik oluşturur ve tüm uygulamayı tek komutla çalıştırır.

### Temel docker-compose.yml
```yaml
version: '3.8'

services:
  web:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
    depends_on:
      - db
    volumes:
      - ./logs:/app/logs

  db:
    image: postgres:13
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

### Gelişmiş docker-compose.yml
```yaml
version: '3.8'

services:
  nginx:
    image: nginx:alpine
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
      - ./ssl:/etc/nginx/ssl
    depends_on:
      - web
    networks:
      - frontend

  web:
    build:
      context: .
      dockerfile: Dockerfile.prod
      args:
        VERSION: ${VERSION:-latest}
    environment:
      - DATABASE_URL=postgresql://user:password@db:5432/myapp
      - REDIS_URL=redis://redis:6379
    depends_on:
      - db
      - redis
    networks:
      - frontend
      - backend
    deploy:
      replicas: 3
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
        reservations:
          cpus: '0.25'
          memory: 256M

  db:
    image: postgres:13
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
    volumes:
      - postgres_data:/var/lib/postgresql/data
    networks:
      - backend
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U user -d myapp"]
      interval: 30s
      timeout: 10s
      retries: 3

  redis:
    image: redis:alpine
    command: redis-server --appendonly yes
    volumes:
      - redis_data:/data
    networks:
      - backend
    healthcheck:
      test: ["CMD", "redis-cli", "ping"]
      interval: 30s
      timeout: 10s
      retries: 3

networks:
  frontend:
  backend:

volumes:
  postgres_data:
  redis_data:
```

### Docker Compose Komutları
```bash
# Servisleri başlat
docker-compose up

# Detached mode'da başlat
docker-compose up -d

# Belirli servisleri başlat
docker-compose up web db

# Servisleri durdur
docker-compose down

# Volume'ları da sil
docker-compose down -v

# Servisleri yeniden başlat
docker-compose restart

# Logları göster
docker-compose logs

# Belirli servisin loglarını göster
docker-compose logs web

# Canlı log takibi
docker-compose logs -f

# Servis durumunu göster
docker-compose ps

# Servisleri build et
docker-compose build

# Belirli servisi build et
docker-compose build web

# Servisleri scale et
docker-compose up --scale web=3
```

---

## 7. Volume ve Bind Mount

**Ne İşe Yarar:** Docker container'larında veri kalıcılığını sağlamak için kullanılan volume ve bind mount yöntemlerini öğretir. Container'lar arasında veri paylaşımını ve yedekleme işlemlerini kapsar.

**Ne Yapar:** Container'ların verilerini kalıcı hale getirir, container'lar arasında dosya paylaşımını sağlar, host sistem ile container arasında veri bağlantısı kurar ve veri yedekleme/geri yükleme işlemlerini kolaylaştırır.

### Volume İşlemleri
```bash
# Volume oluştur
docker volume create my_volume

# Volume listele
docker volume ls

# Volume detaylarını göster
docker volume inspect my_volume

# Volume sil
docker volume rm my_volume

# Kullanılmayan volume'ları sil
docker volume prune
```

### Volume Kullanımı
```bash
# Named volume ile çalıştır
docker run -v my_volume:/app/data ubuntu:latest

# Bind mount ile çalıştır
docker run -v /host/path:/container/path ubuntu:latest

# Read-only bind mount
docker run -v /host/path:/container/path:ro ubuntu:latest

# Docker Compose'da volume
volumes:
  - ./data:/app/data
  - my_volume:/app/storage
```

### Volume Backup ve Restore
```bash
# Volume'u backup et
docker run --rm -v my_volume:/data -v $(pwd):/backup ubuntu tar czf /backup/my_volume_backup.tar.gz -C /data .

# Volume'u restore et
docker run --rm -v my_volume:/data -v $(pwd):/backup ubuntu tar xzf /backup/my_volume_backup.tar.gz -C /data
```

---

## 8. Network İşlemleri

**Ne İşe Yarar:** Docker container'ları arasında iletişimi sağlamak için kullanılan network yapılandırmalarını öğretir. Container'ların birbirleriyle ve dış dünyayla nasıl iletişim kuracağını kapsar.

**Ne Yapar:** Container'lar arasında güvenli iletişim kanalları oluşturur, farklı network türlerini yapılandırır, container'ları network'lere bağlar ve network izolasyonu sağlar.

### Network Oluşturma
```bash
# Bridge network oluştur
docker network create my_network

# Custom driver ile network oluştur
docker network create --driver bridge --subnet=172.18.0.0/16 my_network

# Network listele
docker network ls

# Network detaylarını göster
docker network inspect my_network

# Network sil
docker network rm my_network
```

### Network Kullanımı
```bash
# Container'ı network'e bağla
docker run --network my_network ubuntu:latest

# Container'ı birden fazla network'e bağla
docker network connect my_network container_name

# Container'ı network'ten çıkar
docker network disconnect my_network container_name

# Network'teki container'ları listele
docker network inspect my_network --format='{{range .Containers}}{{.Name}} {{end}}'
```

### Network Türleri
```bash
# Bridge network (varsayılan)
docker network create --driver bridge my_bridge

# Host network
docker run --network host nginx:alpine

# None network (network yok)
docker run --network none ubuntu:latest

# Overlay network (Swarm için)
docker network create --driver overlay my_overlay
```

---

## 9. Registry İşlemleri

**Ne İşe Yarar:** Docker image'larını saklamak ve paylaşmak için kullanılan registry sistemlerini öğretir. Image'ları yayınlama, indirme ve yönetme işlemlerini kapsar.

**Ne Yapar:** Image'ları merkezi bir yerde saklar, image'ları farklı sistemler arasında paylaşır, image versiyonlarını yönetir ve güvenli image dağıtımı sağlar.

### Docker Hub
```bash
# Docker Hub'a login ol
docker login

# Image'ı push et
docker push username/myapp:latest

# Private repository'den pull
docker pull username/myapp:latest
```

### Private Registry
```bash
# Private registry çalıştır
docker run -d -p 5000:5000 --name registry registry:2

# Private registry'ye push
docker tag myapp:latest localhost:5000/myapp:latest
docker push localhost:5000/myapp:latest

# Private registry'den pull
docker pull localhost:5000/myapp:latest
```

### Registry Yönetimi
```bash
# Registry catalog'u listele
curl http://localhost:5000/v2/_catalog

# Repository tag'lerini listele
curl http://localhost:5000/v2/myapp/tags/list

# Image manifest'ini göster
curl http://localhost:5000/v2/myapp/manifests/latest
```

---

## 10. Multi-stage Builds

**Ne İşe Yarar:** Docker image'larının boyutunu küçültmek ve güvenliği artırmak için kullanılan multi-stage build tekniklerini öğretir. Build sürecini optimize etmek için farklı aşamaları kapsar.

**Ne Yapar:** Build sürecini birden fazla aşamaya böler, gereksiz dosyaları final image'dan çıkarır, build araçlarını production image'ından ayırır ve daha güvenli ve küçük image'lar oluşturur.

### Temel Multi-stage Build
```dockerfile
# Build stage
FROM node:16 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

# Production stage
FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### Gelişmiş Multi-stage Build
```dockerfile
# Dependencies stage
FROM node:16 AS deps
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production && npm cache clean --force

# Build stage
FROM node:16 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

# Test stage
FROM builder AS test
RUN npm run test

# Production stage
FROM node:16-alpine AS production
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY --from=builder /app/dist ./dist
COPY package*.json ./
EXPOSE 3000
CMD ["npm", "start"]
```

---

## 11. Docker Swarm

**Ne İşe Yarar:** Docker container'larını birden fazla sunucuda yönetmek için kullanılan Docker Swarm orchestration sistemini öğretir. Container cluster'larının nasıl oluşturulacağını ve yönetileceğini kapsar.

**Ne Yapar:** Birden fazla Docker host'unu tek bir cluster olarak yönetir, container'ları otomatik olarak dağıtır, yük dengelemesi yapar, servis discovery sağlar ve yüksek erişilebilirlik sunar.

### Swarm Başlatma
```bash
# Swarm'ı başlat
docker swarm init

# Worker node ekle
docker swarm join --token <token> <manager-ip>:2377

# Swarm durumunu kontrol et
docker node ls

# Swarm'ı bırak
docker swarm leave --force
```

### Service Oluşturma
```bash
# Service oluştur
docker service create --name web nginx:alpine

# Service'i port ile oluştur
docker service create --name web --publish 80:80 nginx:alpine

# Service'i replica ile oluştur
docker service create --name web --replicas 3 nginx:alpine

# Service'i update et
docker service update --replicas 5 web

# Service'i sil
docker service rm web
```

### Stack Deployment
```yaml
# docker-stack.yml
version: '3.8'

services:
  web:
    image: nginx:alpine
    ports:
      - "80:80"
    deploy:
      replicas: 3
      update_config:
        parallelism: 1
        delay: 10s
      restart_policy:
        condition: on-failure

  db:
    image: postgres:13
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
    deploy:
      placement:
        constraints:
          - node.role == manager
```

```bash
# Stack deploy et
docker stack deploy -c docker-stack.yml myapp

# Stack'leri listele
docker stack ls

# Stack servislerini listele
docker stack services myapp

# Stack'i sil
docker stack rm myapp
```

---

## 12. Güvenlik

**Ne İşe Yarar:** Docker container'larının güvenliğini sağlamak için kullanılan teknikleri öğretir. Container güvenlik açıklarını önlemek ve güvenli container'lar oluşturmak için gerekli yöntemleri kapsar.

**Ne Yapar:** Container'ları güvenli bir şekilde çalıştırır, güvenlik açıklarını tespit eder, container'ları izole eder, güvenli image'lar oluşturur ve güvenlik politikalarını uygular.

### Non-root User
```dockerfile
# Non-root user oluştur
FROM node:16-alpine
RUN addgroup -g 1001 -S nodejs
RUN adduser -S nextjs -u 1001
USER nextjs
WORKDIR /app
COPY --chown=nextjs:nodejs . .
```

### Security Scanning
```bash
# Docker Scout ile tarama
docker scout cves nginx:alpine

# Trivy ile tarama
trivy image nginx:alpine

# Snyk ile tarama
snyk container test nginx:alpine
```

### Secrets Management
```bash
# Secret oluştur
echo "mysecret" | docker secret create my_secret -

# Secret'ları listele
docker secret ls

# Service'e secret ekle
docker service create --secret my_secret nginx:alpine
```

### Image Signing
```bash
# Image'ı sign et
docker trust sign myapp:latest

# Sign'ları kontrol et
docker trust inspect myapp:latest
```

---

## 13. Monitoring ve Logging

**Ne İşe Yarar:** Docker container'larının performansını izlemek ve loglarını yönetmek için kullanılan araçları öğretir. Container'ların sağlık durumunu kontrol etme ve sorunları tespit etme yöntemlerini kapsar.

**Ne Yapar:** Container'ların kaynak kullanımını izler, performans metriklerini toplar, logları toplar ve analiz eder, sağlık kontrollerini yapar ve sorunları erken tespit eder.

### Container Monitoring
```bash
# Container stats
docker stats

# Belirli container'ın stats'ı
docker stats container_name

# Resource kullanımını detaylı göster
docker stats --format "table {{.Container}}\t{{.CPUPerc}}\t{{.MemUsage}}\t{{.NetIO}}\t{{.BlockIO}}"
```

### Logging Drivers
```bash
# JSON file logging (varsayılan)
docker run --log-driver json-file nginx:alpine

# Syslog logging
docker run --log-driver syslog nginx:alpine

# Journald logging
docker run --log-driver journald nginx:alpine

# Fluentd logging
docker run --log-driver fluentd nginx:alpine
```

### Health Checks
```dockerfile
# Dockerfile'da health check
FROM nginx:alpine
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD curl -f http://localhost/ || exit 1
```

```bash
# Health check durumunu kontrol et
docker inspect --format='{{.State.Health.Status}}' container_name

# Health check loglarını göster
docker inspect --format='{{range .State.Health.Log}}{{.Output}}{{end}}' container_name
```

---

## 14. Optimizasyon

**Ne İşe Yarar:** Docker container'larının ve image'larının performansını artırmak için kullanılan optimizasyon tekniklerini öğretir. Image boyutunu küçültme, build sürecini hızlandırma ve runtime performansını artırma yöntemlerini kapsar.

**Ne Yapar:** Image boyutlarını küçültür, build sürelerini kısaltır, container başlatma sürelerini hızlandırır, kaynak kullanımını optimize eder ve maliyetleri düşürür.

### Image Boyutu Optimizasyonu
```dockerfile
# Alpine Linux kullan
FROM alpine:latest

# Multi-stage build kullan
FROM node:16-alpine AS builder
# ... build işlemleri
FROM alpine:latest
COPY --from=builder /app/dist /app

# Gereksiz dosyaları sil
RUN apt-get update && apt-get install -y package && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# .dockerignore kullan
# node_modules
# .git
# *.log
```

### Build Optimizasyonu
```bash
# Build cache'i temizle
docker build --no-cache .

# Build context'i optimize et
# Sadece gerekli dosyaları kopyala

# Parallel build
docker buildx build --platform linux/amd64,linux/arm64 .
```

### Runtime Optimizasyonu
```bash
# Resource limitleri
docker run --memory=512m --cpus=1.0 nginx:alpine

# CPU ve memory reservation
docker run --memory-reservation=256m --cpus=0.5 nginx:alpine

# OOM killer ayarları
docker run --oom-kill-disable nginx:alpine
```

---

## 15. Troubleshooting

**Ne İşe Yarar:** Docker container'larında karşılaşılan sorunları çözmek için kullanılan debugging ve troubleshooting tekniklerini öğretir. Yaygın hataları tespit etme ve çözme yöntemlerini kapsar.

**Ne Yapar:** Container sorunlarını tespit eder, hata loglarını analiz eder, performans sorunlarını çözer, network problemlerini giderir ve container'ları debug eder.

### Container Debugging
```bash
# Container'a debug shell ile bağlan
docker run --rm -it --entrypoint /bin/sh nginx:alpine

# Container'ın çalışma sürecini göster
docker top container_name

# Container'ın diff'ini göster
docker diff container_name

# Container'ın filesystem'ini incele
docker export container_name | tar -t

# Container'ın network bağlantılarını kontrol et
docker exec container_name netstat -tulpn
```

### Log Analizi
```bash
# Logları filtrele
docker logs container_name | grep ERROR

# Logları zaman damgası ile göster
docker logs -t container_name

# Logları JSON formatında göster
docker logs --format json container_name

# Logları dosyaya kaydet
docker logs container_name > container.log
```

### Network Troubleshooting
```bash
# Network bağlantısını test et
docker exec container_name ping google.com

# DNS çözümlemesini test et
docker exec container_name nslookup google.com

# Port bağlantısını test et
docker exec container_name telnet host port

# Network interface'lerini göster
docker exec container_name ip addr show
```

### Performance Issues
```bash
# Container resource kullanımını izle
docker stats --no-stream

# Disk I/O kullanımını kontrol et
docker exec container_name iostat

# Memory kullanımını detaylı göster
docker exec container_name cat /proc/meminfo

# CPU kullanımını detaylı göster
docker exec container_name cat /proc/cpuinfo
```

---

## 16. Best Practices

**Ne İşe Yarar:** Docker ile çalışırken uyulması gereken en iyi uygulamaları öğretir. Güvenlik, performans, geliştirme ve production ortamları için önerilen yöntemleri kapsar.

**Ne Yapar:** Güvenli container'lar oluşturur, performansı optimize eder, geliştirme süreçlerini iyileştirir, production ortamlarını güvenli hale getirir ve Docker kullanımını standartlaştırır.

### Security Best Practices
```dockerfile
# Non-root user kullan
USER 1000:1000

# Minimal base image kullan
FROM alpine:latest

# Güncel image'lar kullan
FROM ubuntu:20.04

# Gereksiz paketleri yükleme
RUN apt-get update && apt-get install -y \
    only-required-package \
    && rm -rf /var/lib/apt/lists/*

# Secrets'ları environment variable olarak geçme
# Bunun yerine Docker secrets kullan
```

### Performance Best Practices
```dockerfile
# Layer cache'leme
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .

# Multi-stage build kullan
FROM node:16 AS builder
# ... build
FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html

# .dockerignore kullan
# node_modules
# .git
# *.log
```

### Development Best Practices
```yaml
# docker-compose.dev.yml
version: '3.8'
services:
  web:
    build: .
    volumes:
      - .:/app
      - /app/node_modules
    environment:
      - NODE_ENV=development
    command: npm run dev
```

---

## 17. CI/CD Entegrasyonu

**Ne İşe Yarar:** Docker container'larını sürekli entegrasyon ve sürekli dağıtım (CI/CD) süreçlerine entegre etmek için kullanılan yöntemleri öğretir. Otomatik build, test ve deployment süreçlerini kapsar.

**Ne Yapar:** Docker image'larını otomatik olarak oluşturur, test eder ve dağıtır, deployment süreçlerini otomatikleştirir, kalite kontrollerini yapar ve sürekli delivery sağlar.

### GitHub Actions
```yaml
# .github/workflows/docker.yml
name: Docker Build and Push

on:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    
    - name: Login to Docker Hub
      uses: docker/login-action@v1
      with:
        username: ${{ secrets.DOCKER_HUB_USERNAME }}
        password: ${{ secrets.DOCKER_HUB_ACCESS_TOKEN }}
    
    - name: Build and push
      uses: docker/build-push-action@v2
      with:
        push: true
        tags: username/myapp:latest
```

### GitLab CI
```yaml
# .gitlab-ci.yml
stages:
  - build
  - deploy

build:
  stage: build
  image: docker:latest
  services:
    - docker:dind
  script:
    - docker build -t myapp:$CI_COMMIT_SHA .
    - docker push myapp:$CI_COMMIT_SHA
```

### Jenkins Pipeline
```groovy
// Jenkinsfile
pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }
        
        stage('Push') {
            steps {
                sh 'docker push myapp'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
```

---

## 18. Cloud Platformları

**Ne İşe Yarar:** Docker container'larını bulut platformlarında çalıştırmak için kullanılan servisleri öğretir. Farklı bulut sağlayıcılarının container servislerini ve entegrasyon yöntemlerini kapsar.

**Ne Yapar:** Container'ları bulut ortamlarında çalıştırır, ölçeklenebilir container servisleri sağlar, bulut kaynaklarını optimize eder, yüksek erişilebilirlik sunar ve maliyet etkin çözümler sağlar.

### AWS ECS
```bash
# ECR'ye push
aws ecr get-login-password --region us-west-2 | docker login --username AWS --password-stdin 123456789012.dkr.ecr.us-west-2.amazonaws.com
docker tag myapp:latest 123456789012.dkr.ecr.us-west-2.amazonaws.com/myapp:latest
docker push 123456789012.dkr.ecr.us-west-2.amazonaws.com/myapp:latest
```

### Google Cloud Run
```bash
# Image'ı GCR'ye push
docker tag myapp:latest gcr.io/PROJECT_ID/myapp:latest
docker push gcr.io/PROJECT_ID/myapp:latest

# Cloud Run'da deploy et
gcloud run deploy myapp --image gcr.io/PROJECT_ID/myapp:latest --platform managed
```

### Azure Container Instances
```bash
# ACR'ye push
az acr login --name myregistry
docker tag myapp:latest myregistry.azurecr.io/myapp:latest
docker push myregistry.azurecr.io/myapp:latest

# Container instance oluştur
az container create --resource-group myResourceGroup --name mycontainer --image myregistry.azurecr.io/myapp:latest
```

---

## 19. Container Orchestration

**Ne İşe Yarar:** Büyük ölçekli container uygulamalarını yönetmek için kullanılan orchestration platformlarını öğretir. Container cluster'larının nasıl yönetileceğini ve ölçeklendirileceğini kapsar.

**Ne Yapar:** Binlerce container'ı yönetir, otomatik ölçeklendirme sağlar, yük dengelemesi yapar, servis discovery sağlar, rolling updates yapar ve yüksek erişilebilirlik sunar.

### Kubernetes
```yaml
# deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp
        image: myapp:latest
        ports:
        - containerPort: 3000
```

### Docker Swarm
```yaml
# docker-stack.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      replicas: 3
      update_config:
        parallelism: 1
        delay: 10s
      restart_policy:
        condition: on-failure
```

### Nomad
```hcl
# job.nomad
job "myapp" {
  datacenters = ["dc1"]
  type = "service"

  group "app" {
    count = 3

    task "web" {
      driver = "docker"

      config {
        image = "nginx:alpine"
        ports = ["http"]
      }

      resources {
        network {
          port "http" {}
        }
      }
    }
  }
}
```

---

## 20. Advanced Docker Features

**Ne İşe Yarar:** Docker'ın gelişmiş özelliklerini ve yeni teknolojilerini öğretir. BuildKit, Docker Extensions, Context ve Plugin gibi modern Docker özelliklerini kapsar.

**Ne Yapar:** Gelişmiş build özellikleri sağlar, Docker'ı genişletir, uzaktan Docker host'larını yönetir, özel plugin'ler ekler ve Docker deneyimini iyileştirir.

### BuildKit
```bash
# BuildKit'i etkinleştir
export DOCKER_BUILDKIT=1

# BuildKit ile build et
docker build --progress=plain .

# Parallel build
docker buildx build --platform linux/amd64,linux/arm64 .
```

### Docker Extensions
```bash
# Extension'ları listele
docker extension ls

# Extension yükle
docker extension install extension-name

# Extension'ı kaldır
docker extension uninstall extension-name
```

### Docker Context
```bash
# Context oluştur
docker context create remote --docker "host=ssh://user@remote-host"

# Context'i değiştir
docker context use remote

# Context'leri listele
docker context ls
```

### Docker Plugin
```bash
# Plugin'leri listele
docker plugin ls

# Plugin yükle
docker plugin install plugin-name

# Plugin'i etkinleştir
docker plugin enable plugin-name
```

---

## 21. Docker Desktop

**Ne İşe Yarar:** Docker'ın masaüstü uygulamasını öğretir. Windows ve macOS'ta Docker'ı kolayca kullanmak için geliştirilmiş GUI arayüzünü kapsar.

**Ne Yapar:** Docker'ı görsel arayüz ile yönetir, container'ları ve image'ları görsel olarak izler, Docker Hub entegrasyonu sağlar ve geliştirme ortamını kolaylaştırır.

### Docker Desktop Kurulumu
```bash
# macOS için Homebrew ile
brew install --cask docker

# Windows için Chocolatey ile
choco install docker-desktop

# Manuel kurulum
# https://www.docker.com/products/docker-desktop
```

### Docker Desktop Özellikleri
```bash
# Docker Desktop ayarları
# Preferences > Resources > Advanced
# Memory: 4GB
# CPUs: 2
# Swap: 1GB

# Docker Desktop extensions
docker extension install docker/desktop-extension-template

# Docker Desktop'ı başlat
open -a Docker
```

---

## 22. Docker Buildx

**Ne İşe Yarar:** Docker'ın gelişmiş build sistemi olan Buildx'i öğretir. Multi-platform image build'leri ve gelişmiş build özelliklerini kapsar.

**Ne Yapar:** Farklı platformlar için image'lar oluşturur, build cache'ini optimize eder, parallel build'leri destekler ve gelişmiş build özellikleri sağlar.

### Buildx Kurulumu
```bash
# Buildx'i etkinleştir
export DOCKER_BUILDKIT=1

# Buildx driver'ını kontrol et
docker buildx ls

# Yeni builder oluştur
docker buildx create --name mybuilder --use
```

### Multi-platform Build
```bash
# Farklı platformlar için build
docker buildx build --platform linux/amd64,linux/arm64 -t myapp:latest .

# Build ve push
docker buildx build --platform linux/amd64,linux/arm64 --push -t myapp:latest .

# Build cache kullan
docker buildx build --cache-from type=registry,ref=myapp:cache --cache-to type=registry,ref=myapp:cache .
```

---

## 23. Docker Scan

**Ne İşe Yarar:** Docker image'larında güvenlik açıklarını tespit etmek için kullanılan Docker Scan aracını öğretir. Güvenlik taraması ve güvenlik açığı analizi yapar.

**Ne Yapar:** Image'larda güvenlik açıklarını tespit eder, CVE veritabanını kontrol eder, güvenlik raporları oluşturur ve güvenlik önerileri sunar.

### Docker Scan Kullanımı
```bash
# Image'ı tara
docker scan nginx:alpine

# Detaylı tarama
docker scan --severity high nginx:alpine

# JSON formatında çıktı
docker scan --format json nginx:alpine

# Tarama raporunu dosyaya kaydet
docker scan nginx:alpine > scan_report.txt
```

### Snyk Entegrasyonu
```bash
# Snyk ile tarama
docker scan --login
docker scan nginx:alpine

# Snyk policy ile tarama
docker scan --policy-path .snyk nginx:alpine
```

---

## 24. Docker Trust

**Ne İşe Yarar:** Docker image'larının güvenliğini sağlamak için kullanılan Docker Trust sistemini öğretir. Image imzalama ve doğrulama işlemlerini kapsar.

**Ne Yapar:** Image'ları dijital olarak imzalar, image bütünlüğünü doğrular, güvenli image dağıtımı sağlar ve image kaynağını garanti eder.

### Docker Trust Kurulumu
```bash
# Trust'ı etkinleştir
export DOCKER_CONTENT_TRUST=1

# Trust durumunu kontrol et
docker trust inspect myapp:latest

# Trust key oluştur
docker trust key generate mykey
```

### Image İmzalama
```bash
# Image'ı imzala
docker trust sign myapp:latest

# Repository'yi imzala
docker trust signer add --key mykey.pub myname myapp

# İmzalı image'ı push et
docker push myapp:latest
```

---

## 25. Docker Content Trust

**Ne İşe Yarar:** Docker image'larının içerik güvenliğini sağlamak için kullanılan Content Trust sistemini öğretir. Image bütünlüğü ve kaynak doğrulamasını kapsar.

**Ne Yapar:** Image'ların değiştirilmediğini garanti eder, güvenilir kaynaklardan gelen image'ları doğrular, image bütünlüğünü korur ve güvenli image kullanımını sağlar.

### Content Trust Yapılandırması
```bash
# Content Trust'ı etkinleştir
export DOCKER_CONTENT_TRUST=1

# Trust server'ı yapılandır
export DOCKER_CONTENT_TRUST_SERVER=https://notary.docker.io

# Trust key'leri yönet
docker trust key load mykey.pem
```

### Güvenli Image Kullanımı
```bash
# Sadece imzalı image'ları kabul et
docker pull myapp:latest

# Trust durumunu kontrol et
docker trust inspect myapp:latest

# Trust key'leri listele
docker trust key list
```

---

## 26. Docker Secrets

**Ne İşe Yarar:** Docker Swarm'da hassas bilgileri güvenli bir şekilde yönetmek için kullanılan Docker Secrets sistemini öğretir. Şifreler, API anahtarları ve diğer hassas verileri kapsar.

**Ne Yapar:** Hassas bilgileri şifreler, güvenli dağıtım sağlar, secret'ları container'lara güvenli şekilde aktarır ve secret yönetimini merkezi hale getirir.

### Secret Oluşturma
```bash
# Secret oluştur
echo "mysecretpassword" | docker secret create db_password -

# Dosyadan secret oluştur
docker secret create ssl_cert ./cert.pem

# Secret'ları listele
docker secret ls

# Secret detaylarını göster
docker secret inspect db_password
```

### Secret Kullanımı
```bash
# Service'e secret ekle
docker service create --secret db_password nginx:alpine

# Compose'da secret kullan
version: '3.8'
services:
  web:
    image: nginx:alpine
    secrets:
      - db_password
secrets:
  db_password:
    external: true
```

---

## 27. Docker Configs

**Ne İşe Yarar:** Docker Swarm'da yapılandırma dosyalarını yönetmek için kullanılan Docker Configs sistemini öğretir. Uygulama konfigürasyonlarını ve ayar dosyalarını kapsar.

**Ne Yapar:** Yapılandırma dosyalarını merkezi olarak yönetir, config'leri container'lara güvenli şekilde aktarır, config versiyonlarını yönetir ve config dağıtımını otomatikleştirir.

### Config Oluşturma
```bash
# Config oluştur
echo "server { listen 80; }" | docker config create nginx_config -

# Dosyadan config oluştur
docker config create app_config ./config.json

# Config'leri listele
docker config ls

# Config detaylarını göster
docker config inspect nginx_config
```

### Config Kullanımı
```bash
# Service'e config ekle
docker service create --config nginx_config nginx:alpine

# Compose'da config kullan
version: '3.8'
services:
  web:
    image: nginx:alpine
    configs:
      - source: nginx_config
        target: /etc/nginx/nginx.conf
configs:
  nginx_config:
    external: true
```

---

## 28. Docker Events

**Ne İşe Yarar:** Docker sisteminde gerçekleşen olayları izlemek için kullanılan Docker Events sistemini öğretir. Container, image ve sistem olaylarını kapsar.

**Ne Yapar:** Docker sistemindeki değişiklikleri gerçek zamanlı olarak izler, olayları filtreler, olay loglarını tutar ve sistem aktivitelerini takip eder.

### Events İzleme
```bash
# Tüm olayları izle
docker events

# Belirli olayları filtrele
docker events --filter 'type=container' --filter 'event=start'

# JSON formatında olaylar
docker events --format '{{json .}}'

# Olayları dosyaya kaydet
docker events > docker_events.log
```

### Event Filtreleme
```bash
# Container olayları
docker events --filter 'type=container'

# Image olayları
docker events --filter 'type=image'

# Belirli container'ın olayları
docker events --filter 'container=mycontainer'

# Belirli zaman aralığındaki olaylar
docker events --since '2023-01-01' --until '2023-12-31'
```

---

## 29. Docker System

**Ne İşe Yarar:** Docker sistemini yönetmek için kullanılan Docker System komutlarını öğretir. Sistem kaynaklarını izleme, temizlik ve yönetim işlemlerini kapsar.

**Ne Yapar:** Docker sisteminin durumunu kontrol eder, kaynak kullanımını izler, gereksiz kaynakları temizler, sistem performansını optimize eder ve disk alanını yönetir.

### Sistem Bilgileri
```bash
# Sistem kullanımını göster
docker system df

# Detaylı sistem bilgileri
docker system df -v

# Sistem durumunu kontrol et
docker system info
```

### Sistem Temizliği
```bash
# Kullanılmayan kaynakları temizle
docker system prune

# Tüm kullanılmayan kaynakları temizle
docker system prune -a

# Volume'ları da temizle
docker system prune --volumes

# Belirli zaman öncesindeki kaynakları temizle
docker system prune --filter "until=24h"
```

---

## 30. Docker Context

**Ne İşe Yarar:** Farklı Docker host'ları arasında geçiş yapmak için kullanılan Docker Context sistemini öğretir. Uzaktan Docker yönetimi ve multi-environment yapılandırmasını kapsar.

**Ne Yapar:** Farklı Docker ortamları arasında geçiş yapar, uzaktan Docker host'larını yönetir, context'leri organize eder ve Docker yönetimini kolaylaştırır.

### Context Oluşturma
```bash
# Context oluştur
docker context create remote --docker "host=ssh://user@remote-host"

# Context'i değiştir
docker context use remote

# Context'leri listele
docker context ls

# Context detaylarını göster
docker context inspect remote
```

### Context Yönetimi
```bash
# Context'i güncelle
docker context update remote --docker "host=ssh://user@new-host"

# Context'i sil
docker context rm remote

# Context'i export et
docker context export remote > remote-context.yaml

# Context'i import et
docker context import remote remote-context.yaml
```

---

## Faydalı Komutlar ve Kısayollar

### Günlük Kullanım
```bash
# Tüm container'ları durdur
docker stop $(docker ps -q)

# Tüm container'ları sil
docker rm $(docker ps -aq)

# Tüm image'ları sil
docker rmi $(docker images -q)

# Disk kullanımını temizle
docker system prune -a

# Container'ı yeniden başlat
docker restart container_name

# Container loglarını takip et
docker logs -f container_name
```

### Debug Komutları
```bash
# Container'a bash ile bağlan
docker exec -it container_name /bin/bash

# Container'ın çalışma sürecini göster
docker top container_name

# Container'ın diff'ini göster
docker diff container_name

# Container'ın filesystem'ini incele
docker export container_name | tar -t
```

### Monitoring Komutları
```bash
# Container stats
docker stats

# Resource kullanımını detaylı göster
docker stats --format "table {{.Container}}\t{{.CPUPerc}}\t{{.MemUsage}}\t{{.NetIO}}\t{{.BlockIO}}"

# Health check durumu
docker inspect --format='{{.State.Health.Status}}' container_name
```

---

## Sık Karşılaşılan Hatalar ve Çözümleri

### Permission Denied
```bash
# Docker socket permission hatası
sudo chmod 666 /var/run/docker.sock

# Veya kullanıcıyı docker grubuna ekle
sudo usermod -aG docker $USER
```

### Port Already in Use
```bash
# Port'u kullanan process'i bul
sudo lsof -i :8080

# Process'i sonlandır
sudo kill -9 PID

# Veya farklı port kullan
docker run -p 8081:80 nginx:alpine
```

### Out of Memory
```bash
# Memory limitini artır
docker run --memory=1g nginx:alpine

# Swap kullan
docker run --memory=512m --memory-swap=1g nginx:alpine
```

### Image Pull Failed
```bash
# Registry'ye login ol
docker login

# Network bağlantısını kontrol et
ping registry-1.docker.io

# DNS ayarlarını kontrol et
nslookup registry-1.docker.io
```

---

## 31. Docker Plugin

**Ne İşe Yarar:** Docker'ı genişletmek için kullanılan Docker Plugin sistemini öğretir. Özel işlevsellik eklemek ve Docker'ı özelleştirmek için kullanılan plugin'leri kapsar.

**Ne Yapar:** Docker'a yeni komutlar ekler, özel işlevsellik sağlar, üçüncü parti araçları entegre eder ve Docker deneyimini kişiselleştirir.

### Plugin Kurulumu
```bash
# Plugin'leri listele
docker plugin ls

# Plugin yükle
docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions

# Plugin'i etkinleştir
docker plugin enable loki

# Plugin'i devre dışı bırak
docker plugin disable loki

# Plugin'i kaldır
docker plugin rm loki
```

### Plugin Yönetimi
```bash
# Plugin detaylarını göster
docker plugin inspect loki

# Plugin'i güncelle
docker plugin upgrade loki grafana/loki-docker-driver:latest

# Plugin'i yapılandır
docker plugin set loki key=value

# Plugin loglarını göster
docker plugin logs loki
```

---

## 32. Docker Extension

**Ne İşe Yarar:** Docker Desktop'a özel işlevsellik eklemek için kullanılan Docker Extension sistemini öğretir. GUI tabanlı uzantıları ve görsel araçları kapsar.

**Ne Yapar:** Docker Desktop'a yeni özellikler ekler, görsel arayüzler sağlar, geliştirme araçlarını entegre eder ve Docker deneyimini iyileştirir.

### Extension Kurulumu
```bash
# Extension'ları listele
docker extension ls

# Extension yükle
docker extension install docker/desktop-extension-template

# Extension'ı kaldır
docker extension uninstall extension-name

# Extension'ı etkinleştir
docker extension enable extension-name
```

### Extension Geliştirme
```bash
# Extension template'i oluştur
docker extension init my-extension

# Extension'ı build et
docker extension build my-extension

# Extension'ı test et
docker extension dev my-extension
```

---

## 33. Docker Scout

**Ne İşe Yarar:** Docker image'larının güvenlik ve kalitesini analiz etmek için kullanılan Docker Scout aracını öğretir. Güvenlik açıklarını tespit etme ve image kalitesini değerlendirme işlemlerini kapsar.

**Ne Yapar:** Image'larda güvenlik açıklarını tespit eder, image kalitesini değerlendirir, güvenlik önerileri sunar, compliance raporları oluşturur ve güvenlik politikalarını uygular.

### Scout Kullanımı
```bash
# Image'ı analiz et
docker scout cves nginx:alpine

# Detaylı analiz
docker scout quickview nginx:alpine

# Güvenlik raporu oluştur
docker scout cves --format sarif nginx:alpine > report.sarif

# Policy kontrolü
docker scout policy nginx:alpine
```

### Scout Yapılandırması
```bash
# Scout'u yapılandır
docker scout config

# Policy dosyası oluştur
docker scout policy create my-policy

# Policy'yi uygula
docker scout policy apply my-policy nginx:alpine
```

---

## 34. Docker Dev Environments

**Ne İşe Yarar:** Geliştirme ortamlarını Docker ile yönetmek için kullanılan Docker Dev Environments sistemini öğretir. Geliştirme ortamlarının oluşturulması ve paylaşılmasını kapsar.

**Ne Yapar:** Geliştirme ortamlarını containerize eder, ortamları paylaşır, geliştirme süreçlerini standartlaştırır ve takım çalışmasını kolaylaştırır.

### Dev Environment Oluşturma
```bash
# Dev environment oluştur
docker dev init my-project

# Dev environment'ı başlat
docker dev up

# Dev environment'ı durdur
docker dev down

# Dev environment'ı paylaş
docker dev share
```

### Dev Environment Yönetimi
```bash
# Dev environment'ları listele
docker dev ls

# Dev environment detayları
docker dev inspect my-project

# Dev environment'ı güncelle
docker dev update my-project

# Dev environment'ı sil
docker dev rm my-project
```

---

## 35. Docker Compose V2

**Ne İşe Yarar:** Docker Compose'un yeni versiyonunu öğretir. Gelişmiş özellikler, performans iyileştirmeleri ve yeni komut yapısını kapsar.

**Ne Yapar:** Daha hızlı çalışır, daha az kaynak kullanır, yeni özellikler sağlar, geriye uyumluluk sunar ve gelişmiş hata yönetimi yapar.

### Compose V2 Komutları
```bash
# Compose V2 kullan
docker compose up

# Detached mode
docker compose up -d

# Build ve up
docker compose up --build

# Belirli servisleri çalıştır
docker compose up web db

# Compose durumunu kontrol et
docker compose ps
```

### Compose V2 Özellikleri
```bash
# Parallel build
docker compose build --parallel

# Build cache kullan
docker compose build --no-cache

# Service scale
docker compose up --scale web=3

# Health check bekle
docker compose up --wait
```

---

## 36. Docker Compose Profiles

**Ne İşe Yarar:** Docker Compose'da farklı ortamlar için profil sistemi kullanımını öğretir. Geliştirme, test ve production ortamları için farklı servis kombinasyonlarını kapsar.

**Ne Yapar:** Ortam bazlı servis seçimi yapar, gereksiz servisleri devre dışı bırakır, ortam yönetimini kolaylaştırır ve kaynak kullanımını optimize eder.

### Profile Tanımlama
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    profiles: ["prod", "staging"]
  
  db:
    image: postgres:13
    profiles: ["prod", "dev"]
  
  redis:
    image: redis:alpine
    profiles: ["dev", "test"]
  
  monitoring:
    image: prometheus:latest
    profiles: ["prod"]
```

### Profile Kullanımı
```bash
# Belirli profil ile çalıştır
docker compose --profile prod up

# Birden fazla profil
docker compose --profile prod --profile monitoring up

# Profil listesini göster
docker compose config --profiles

# Profil ile build
docker compose --profile dev build
```

---

## 37. Docker Compose Override

**Ne İşe Yarar:** Docker Compose dosyalarını farklı ortamlar için özelleştirmek için kullanılan override sistemini öğretir. Ortam bazlı yapılandırma değişikliklerini kapsar.

**Ne Yapar:** Temel yapılandırmayı korur, ortam bazlı değişiklikler yapar, yapılandırma yönetimini kolaylaştırır ve kod tekrarını önler.

### Override Dosyası Oluşturma
```yaml
# docker-compose.override.yml
version: '3.8'
services:
  web:
    environment:
      - NODE_ENV=development
    volumes:
      - .:/app
      - /app/node_modules
    command: npm run dev
  
  db:
    environment:
      POSTGRES_PASSWORD: dev_password
```

### Override Kullanımı
```bash
# Override ile çalıştır
docker compose up

# Belirli override dosyası
docker compose -f docker-compose.yml -f docker-compose.dev.yml up

# Override olmadan çalıştır
docker compose -f docker-compose.yml up

# Override yapılandırmasını göster
docker compose config
```

---

## 38. Docker Compose Extensions

**Ne İşe Yarar:** Docker Compose'a özel işlevsellik eklemek için kullanılan extension sistemini öğretir. Compose dosyalarını genişletmek ve özel işlevler eklemek için kullanılan yöntemleri kapsar.

**Ne Yapar:** Compose dosyalarını genişletir, özel işlevler ekler, yapılandırma yönetimini iyileştirir ve Compose deneyimini özelleştirir.

### Extension Tanımlama
```yaml
# docker-compose.yml
version: '3.8'
x-logging: &default-logging
  driver: "json-file"
  options:
    max-size: "10m"
    max-file: "3"

services:
  web:
    image: nginx:alpine
    logging: *default-logging
  
  db:
    image: postgres:13
    logging: *default-logging
```

### Extension Kullanımı
```yaml
# Ortak yapılandırmalar
x-common-env: &common-env
  TZ: UTC
  LANG: en_US.UTF-8

services:
  app1:
    image: myapp:latest
    environment:
      <<: *common-env
      APP_NAME: app1
  
  app2:
    image: myapp:latest
    environment:
      <<: *common-env
      APP_NAME: app2
```

---

## 39. Docker Compose Watch

**Ne İşe Yarar:** Dosya değişikliklerini izleyerek otomatik yeniden başlatma yapan Docker Compose Watch özelliğini öğretir. Geliştirme sürecini hızlandırmak için kullanılan otomatik yenileme sistemini kapsar.

**Ne Yapar:** Dosya değişikliklerini izler, otomatik yeniden başlatma yapar, geliştirme sürecini hızlandırır, hot reload sağlar ve geliştirici deneyimini iyileştirir.

### Watch Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    build: .
    develop:
      watch:
        - action: sync
          path: ./src
          target: /app/src
        - action: rebuild
          path: ./package.json
        - action: sync
          path: ./public
          target: /app/public
          ignore:
            - node_modules/
```

### Watch Kullanımı
```bash
# Watch modunda başlat
docker compose watch

# Belirli servisi izle
docker compose watch web

# Watch durumunu kontrol et
docker compose watch --status

# Watch'ı durdur
docker compose watch --stop
```

---

## 40. Docker Compose Build

**Ne İşe Yarar:** Docker Compose ile image build işlemlerini yönetmek için kullanılan build sistemini öğretir. Multi-service build'leri ve build optimizasyonlarını kapsar.

**Ne Yapar:** Birden fazla servisi aynı anda build eder, build cache'ini optimize eder, build süreçlerini yönetir, build bağımlılıklarını çözer ve build performansını artırır.

### Build Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    build:
      context: ./frontend
      dockerfile: Dockerfile
      args:
        NODE_ENV: production
      target: production
      cache_from:
        - myapp:cache
      cache_to:
        - myapp:cache
  
  api:
    build:
      context: ./backend
      dockerfile: Dockerfile
      args:
        VERSION: latest
```

### Build Komutları
```bash
# Tüm servisleri build et
docker compose build

# Belirli servisi build et
docker compose build web

# Build cache'i temizle
docker compose build --no-cache

# Parallel build
docker compose build --parallel

# Build ve push
docker compose build --push
```

---

## 41. Docker Compose Deploy

**Ne İşe Yarar:** Docker Compose ile deployment işlemlerini yönetmek için kullanılan deploy sistemini öğretir. Production ortamlarına deployment ve servis yönetimini kapsar.

**Ne Yapar:** Servisleri production ortamına dağıtır, deployment stratejilerini uygular, servis güncellemelerini yönetir, rollback işlemlerini sağlar ve deployment süreçlerini otomatikleştirir.

### Deploy Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      replicas: 3
      update_config:
        parallelism: 1
        delay: 10s
        order: start-first
      restart_policy:
        condition: on-failure
        delay: 5s
        max_attempts: 3
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
        reservations:
          cpus: '0.25'
          memory: 256M
```

### Deploy Komutları
```bash
# Servisleri deploy et
docker compose deploy

# Belirli servisi deploy et
docker compose deploy web

# Deploy durumunu kontrol et
docker compose ps

# Deploy loglarını göster
docker compose logs
```

---

## 42. Docker Compose Config

**Ne İşe Yarar:** Docker Compose yapılandırma dosyalarını doğrulamak ve görüntülemek için kullanılan config komutunu öğretir. Yapılandırma analizi ve doğrulama işlemlerini kapsar.

**Ne Yapar:** Compose dosyalarını doğrular, yapılandırma hatalarını tespit eder, birleştirilmiş yapılandırmayı gösterir, yapılandırma analizi yapar ve deployment öncesi kontrol sağlar.

### Config Komutları
```bash
# Yapılandırmayı doğrula
docker compose config

# Detaylı çıktı
docker compose config --verbose

# JSON formatında çıktı
docker compose config --format json

# Yapılandırmayı dosyaya kaydet
docker compose config > final-compose.yml

# Sadece belirli servisleri
docker compose config --services
```

### Config Analizi
```bash
# Yapılandırma hatalarını kontrol et
docker compose config --quiet

# Yapılandırma değişkenlerini göster
docker compose config --variables

# Yapılandırma bağımlılıklarını analiz et
docker compose config --resolve-image-digests
```

---

## 43. Docker Compose Convert

**Ne İşe Yarar:** Docker Compose dosyalarını farklı formatlara dönüştürmek için kullanılan convert komutunu öğretir. Format dönüşümleri ve uyumluluk işlemlerini kapsar.

**Ne Yapar:** Compose dosyalarını farklı formatlara çevirir, versiyon uyumluluğunu sağlar, format dönüşümlerini yapar, uyumluluk sorunlarını çözer ve format standardizasyonu sağlar.

### Convert Kullanımı
```bash
# Compose dosyasını dönüştür
docker compose convert

# Belirli versiyona dönüştür
docker compose convert --compose-version 3.8

# JSON formatına dönüştür
docker compose convert --format json

# Kubernetes formatına dönüştür
docker compose convert --format kubernetes

# Dönüştürülmüş dosyayı kaydet
docker compose convert > converted-compose.yml
```

### Format Dönüşümleri
```bash
# Eski versiyondan yeni versiyona
docker compose convert --from 2.4 --to 3.8

# Swarm formatına dönüştür
docker compose convert --format swarm

# Helm chart formatına dönüştür
docker compose convert --format helm
```

---

## 44. Docker Compose Pull

**Ne İşe Yarar:** Docker Compose ile image'ları registry'lerden indirmek için kullanılan pull komutunu öğretir. Image indirme ve güncelleme işlemlerini kapsar.

**Ne Yapar:** Compose dosyasındaki image'ları indirir, image güncellemelerini kontrol eder, image bağımlılıklarını çözer, image cache'ini yönetir ve image indirme süreçlerini optimize eder.

### Pull Komutları
```bash
# Tüm image'ları indir
docker compose pull

# Belirli servisin image'ını indir
docker compose pull web

# Parallel indirme
docker compose pull --parallel

# Quiet mode
docker compose pull --quiet

# Ignore pull failures
docker compose pull --ignore-pull-failures
```

### Pull Stratejileri
```bash
# Sadece eksik image'ları indir
docker compose pull --include-deps

# Tüm image'ları yeniden indir
docker compose pull --force

# Belirli tag'leri indir
docker compose pull --tag latest
```

---

## 45. Docker Compose Push

**Ne İşe Yarar:** Docker Compose ile image'ları registry'lere göndermek için kullanılan push komutunu öğretir. Image yayınlama ve dağıtım işlemlerini kapsar.

**Ne Yapar:** Build edilen image'ları registry'lere gönderir, image dağıtımını sağlar, image versiyonlarını yönetir, image paylaşımını kolaylaştırır ve deployment süreçlerini otomatikleştirir.

### Push Komutları
```bash
# Tüm image'ları push et
docker compose push

# Belirli servisin image'ını push et
docker compose push web

# Parallel push
docker compose push --parallel

# Ignore push failures
docker compose push --ignore-push-failures

# Push ve tag
docker compose push --tag latest
```

### Push Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    build: .
    image: myapp:latest
    push: true
  
  api:
    build: ./api
    image: myapp-api:latest
    push: true
```

---

## 46. Docker Compose Scale

**Ne İşe Yarar:** Docker Compose ile servis replikalarını yönetmek için kullanılan scale komutunu öğretir. Servis ölçeklendirme ve yük dengeleme işlemlerini kapsar.

**Ne Yapar:** Servis replika sayısını değiştirir, yük dengelemesi sağlar, ölçeklendirme işlemlerini yönetir, kaynak kullanımını optimize eder ve performansı artırır.

### Scale Komutları
```bash
# Servisi ölçeklendir
docker compose up --scale web=3

# Belirli servisi ölçeklendir
docker compose scale web=5

# Birden fazla servisi ölçeklendir
docker compose scale web=3 db=2

# Ölçeklendirme durumunu kontrol et
docker compose ps

# Ölçeklendirme loglarını göster
docker compose logs
```

### Scale Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      replicas: 3
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
```

---

## 47. Docker Compose Top

**Ne İşe Yarar:** Docker Compose ile çalışan servislerin process bilgilerini görüntülemek için kullanılan top komutunu öğretir. Process izleme ve sistem kaynaklarını kapsar.

**Ne Yapar:** Çalışan servislerin process'lerini gösterir, sistem kaynaklarını izler, process detaylarını sağlar, performans analizi yapar ve sistem durumunu takip eder.

### Top Komutları
```bash
# Tüm servislerin process'lerini göster
docker compose top

# Belirli servisin process'lerini göster
docker compose top web

# Detaylı process bilgileri
docker compose top --verbose

# Process bilgilerini formatla
docker compose top --format table
```

### Process Analizi
```bash
# CPU kullanımını göster
docker compose top --cpu

# Memory kullanımını göster
docker compose top --memory

# Process sayısını göster
docker compose top --count
```

---

## 48. Docker Compose Pause

**Ne İşe Yarar:** Docker Compose ile servisleri duraklatmak için kullanılan pause komutunu öğretir. Servis duraklatma ve devam ettirme işlemlerini kapsar.

**Ne Yapar:** Servisleri duraklatır, kaynak kullanımını azaltır, servis durumunu korur, hızlı durdurma/başlatma sağlar ve geçici durdurma işlemlerini yönetir.

### Pause Komutları
```bash
# Tüm servisleri duraklat
docker compose pause

# Belirli servisi duraklat
docker compose pause web

# Birden fazla servisi duraklat
docker compose pause web db

# Duraklatma durumunu kontrol et
docker compose ps

# Duraklatılmış servisleri listele
docker compose ps --filter "paused"
```

### Pause Yönetimi
```bash
# Duraklatılmış servisleri devam ettir
docker compose unpause

# Belirli servisi devam ettir
docker compose unpause web

# Duraklatma süresini kontrol et
docker compose ps --format "table {{.Name}}\t{{.Status}}\t{{.RunningFor}}"
```

---

## 49. Docker Compose Unpause

**Ne İşe Yarar:** Docker Compose ile duraklatılmış servisleri devam ettirmek için kullanılan unpause komutunu öğretir. Servis devam ettirme ve yeniden başlatma işlemlerini kapsar.

**Ne Yapar:** Duraklatılmış servisleri devam ettirir, servis durumunu geri yükler, kaynak kullanımını artırır, servis erişilebilirliğini sağlar ve normal çalışma durumuna döndürür.

### Unpause Komutları
```bash
# Tüm servisleri devam ettir
docker compose unpause

# Belirli servisi devam ettir
docker compose unpause web

# Birden fazla servisi devam ettir
docker compose unpause web db

# Devam ettirme durumunu kontrol et
docker compose ps

# Servis durumunu izle
docker compose logs -f
```

### Unpause Stratejileri
```bash
# Sıralı devam ettirme
docker compose unpause db && docker compose unpause web

# Koşullu devam ettirme
docker compose unpause --wait

# Devam ettirme sonrası kontrol
docker compose ps --filter "running"
```

---

## 50. Docker Compose Kill

**Ne İşe Yarar:** Docker Compose ile servisleri zorla sonlandırmak için kullanılan kill komutunu öğretir. Acil durdurma ve zorla sonlandırma işlemlerini kapsar.

**Ne Yapar:** Servisleri zorla sonlandırır, acil durdurma sağlar, process'leri kill eder, kaynakları serbest bırakır ve sistem kaynaklarını korur.

### Kill Komutları
```bash
# Tüm servisleri kill et
docker compose kill

# Belirli servisi kill et
docker compose kill web

# Belirli sinyal ile kill et
docker compose kill -s SIGTERM web

# Zorla kill et
docker compose kill -s SIGKILL web

# Kill durumunu kontrol et
docker compose ps
```

### Kill Stratejileri
```bash
# Graceful shutdown
docker compose kill -s SIGTERM

# Immediate kill
docker compose kill -s SIGKILL

# Kill ve temizlik
docker compose kill && docker compose down

# Kill sonrası yeniden başlat
docker compose kill && docker compose up -d
```

---

## 51. Docker Compose Exec

**Ne İşe Yarar:** Docker Compose ile çalışan servislerin içine komut çalıştırmak için kullanılan exec komutunu öğretir. Container'lara bağlanma ve komut çalıştırma işlemlerini kapsar.

**Ne Yapar:** Çalışan servislerin içine bağlanır, komutları çalıştırır, debug işlemlerini kolaylaştırır, servis içi işlemleri yönetir ve container'lara interaktif erişim sağlar.

### Exec Komutları
```bash
# Servise bağlan
docker compose exec web bash

# Belirli kullanıcı ile bağlan
docker compose exec -u root web bash

# Komut çalıştır
docker compose exec web ls -la

# Environment variable ile çalıştır
docker compose exec -e DEBUG=1 web npm run test

# Working directory belirt
docker compose exec -w /app web npm install
```

### Exec Stratejileri
```bash
# Birden fazla servise komut çalıştır
docker compose exec web echo "hello" && docker compose exec db echo "world"

# Background'da çalıştır
docker compose exec -d web npm run dev

# TTY olmadan çalıştır
docker compose exec -T web cat /etc/hosts

# Privileged mode
docker compose exec --privileged web mount /dev/sda1 /mnt
```

---

## 52. Docker Compose Run

**Ne İşe Yarar:** Docker Compose ile geçici container'lar çalıştırmak için kullanılan run komutunu öğretir. Tek seferlik görevler ve test işlemlerini kapsar.

**Ne Yapar:** Geçici container'lar oluşturur, tek seferlik komutlar çalıştırır, test ortamları sağlar, debug işlemlerini kolaylaştırır ve geçici servisler çalıştırır.

### Run Komutları
```bash
# Geçici container çalıştır
docker compose run --rm web npm run test

# Belirli servis adı ile çalıştır
docker compose run --rm --service-ports web npm start

# Environment variable ile çalıştır
docker compose run --rm -e NODE_ENV=test web npm test

# Volume mount ile çalıştır
docker compose run --rm -v $(pwd):/app web npm install

# Network belirt
docker compose run --rm --network my-network web curl db:5432
```

### Run Stratejileri
```bash
# Detached mode
docker compose run -d web npm run dev

# Interactive mode
docker compose run -it web bash

# Port mapping
docker compose run --rm -p 3000:3000 web npm start

# Working directory
docker compose run --rm -w /app web npm install
```

---

## 53. Docker Compose Port

**Ne İşe Yarar:** Docker Compose ile servislerin port mapping'lerini görüntülemek için kullanılan port komutunu öğretir. Port bağlantılarını ve network yapılandırmasını kapsar.

**Ne Yapar:** Servislerin port mapping'lerini gösterir, network bağlantılarını listeler, port durumunu kontrol eder, port çakışmalarını tespit eder ve port yönetimini kolaylaştırır.

### Port Komutları
```bash
# Tüm port mapping'leri göster
docker compose port

# Belirli servisin port mapping'ini göster
docker compose port web 80

# Belirli port'u göster
docker compose port web 3000

# JSON formatında çıktı
docker compose port --format json

# Port durumunu kontrol et
docker compose port --quiet
```

### Port Analizi
```bash
# Port çakışmalarını kontrol et
docker compose port | grep -E ":[0-9]+"

# Belirli port'u kullanan servisleri bul
docker compose port | grep ":80"

# Port mapping'lerini dosyaya kaydet
docker compose port > port_mappings.txt
```

---

## 54. Docker Compose Images

**Ne İşe Yarar:** Docker Compose ile kullanılan image'ları görüntülemek için kullanılan images komutunu öğretir. Image bilgilerini ve durumunu kapsar.

**Ne Yapar:** Compose servislerinin image'larını listeler, image detaylarını gösterir, image durumunu kontrol eder, image bağımlılıklarını analiz eder ve image yönetimini kolaylaştırır.

### Images Komutları
```bash
# Tüm image'ları listele
docker compose images

# Belirli servisin image'ını göster
docker compose images web

# Detaylı image bilgileri
docker compose images --verbose

# Image boyutlarını göster
docker compose images --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}"

# Sadece image ID'lerini göster
docker compose images -q
```

### Image Analizi
```bash
# Kullanılmayan image'ları bul
docker compose images --filter "dangling=true"

# Belirli tag'deki image'ları listele
docker compose images --filter "reference=myapp:*"

# Image'ları temizle
docker compose images --filter "dangling=true" -q | xargs docker rmi
```

---

## 55. Docker Compose Volumes

**Ne İşe Yarar:** Docker Compose ile kullanılan volume'ları yönetmek için kullanılan volumes komutunu öğretir. Volume oluşturma, listeleme ve yönetim işlemlerini kapsar.

**Ne Yapar:** Compose volume'larını listeler, volume detaylarını gösterir, volume durumunu kontrol eder, volume yönetimini sağlar ve volume temizliği yapar.

### Volumes Komutları
```bash
# Tüm volume'ları listele
docker compose volumes

# Belirli volume'u göster
docker compose volumes postgres_data

# Detaylı volume bilgileri
docker compose volumes --verbose

# Volume kullanımını göster
docker compose volumes --format "table {{.Name}}\t{{.Driver}}\t{{.Size}}"

# Sadece volume isimlerini göster
docker compose volumes -q
```

### Volume Yönetimi
```bash
# Volume oluştur
docker compose volumes create my_volume

# Volume'u sil
docker compose volumes rm my_volume

# Kullanılmayan volume'ları temizle
docker compose volumes prune

# Volume backup
docker compose volumes backup my_volume
```

---

## 56. Docker Compose Networks

**Ne İşe Yarar:** Docker Compose ile kullanılan network'leri yönetmek için kullanılan networks komutunu öğretir. Network oluşturma, listeleme ve yönetim işlemlerini kapsar.

**Ne Yapar:** Compose network'lerini listeler, network detaylarını gösterir, network durumunu kontrol eder, network yönetimini sağlar ve network bağlantılarını yönetir.

### Networks Komutları
```bash
# Tüm network'leri listele
docker compose networks

# Belirli network'ü göster
docker compose networks my_network

# Detaylı network bilgileri
docker compose networks --verbose

# Network kullanımını göster
docker compose networks --format "table {{.Name}}\t{{.Driver}}\t{{.Scope}}"

# Sadece network isimlerini göster
docker compose networks -q
```

### Network Yönetimi
```bash
# Network oluştur
docker compose networks create my_network

# Network'ü sil
docker compose networks rm my_network

# Network'e servis bağla
docker compose networks connect my_network web

# Network'ten servis çıkar
docker compose networks disconnect my_network web
```

---

## 57. Docker Compose Configs

**Ne İşe Yarar:** Docker Compose ile kullanılan config'leri yönetmek için kullanılan configs komutunu öğretir. Config oluşturma, listeleme ve yönetim işlemlerini kapsar.

**Ne Yapar:** Compose config'lerini listeler, config detaylarını gösterir, config durumunu kontrol eder, config yönetimini sağlar ve config dağıtımını yönetir.

### Configs Komutları
```bash
# Tüm config'leri listele
docker compose configs

# Belirli config'i göster
docker compose configs nginx_config

# Detaylı config bilgileri
docker compose configs --verbose

# Config kullanımını göster
docker compose configs --format "table {{.Name}}\t{{.CreatedAt}}\t{{.UpdatedAt}}"

# Sadece config isimlerini göster
docker compose configs -q
```

### Config Yönetimi
```bash
# Config oluştur
echo "server { listen 80; }" | docker compose configs create nginx_config

# Config'i sil
docker compose configs rm nginx_config

# Config'i güncelle
docker compose configs update nginx_config

# Config'i inspect et
docker compose configs inspect nginx_config
```

---

## 58. Docker Compose Secrets

**Ne İşe Yarar:** Docker Compose ile kullanılan secret'ları yönetmek için kullanılan secrets komutunu öğretir. Secret oluşturma, listeleme ve yönetim işlemlerini kapsar.

**Ne Yapar:** Compose secret'larını listeler, secret detaylarını gösterir, secret durumunu kontrol eder, secret yönetimini sağlar ve güvenli secret dağıtımını yönetir.

### Secrets Komutları
```bash
# Tüm secret'ları listele
docker compose secrets

# Belirli secret'ı göster
docker compose secrets db_password

# Detaylı secret bilgileri
docker compose secrets --verbose

# Secret kullanımını göster
docker compose secrets --format "table {{.Name}}\t{{.CreatedAt}}\t{{.UpdatedAt}}"

# Sadece secret isimlerini göster
docker compose secrets -q
```

### Secret Yönetimi
```bash
# Secret oluştur
echo "mysecretpassword" | docker compose secrets create db_password

# Secret'ı sil
docker compose secrets rm db_password

# Secret'ı güncelle
docker compose secrets update db_password

# Secret'ı inspect et
docker compose secrets inspect db_password
```

---

## 59. Docker Compose Healthcheck

**Ne İşe Yarar:** Docker Compose ile servislerin sağlık durumunu kontrol etmek için kullanılan healthcheck sistemini öğretir. Servis sağlığı izleme ve kontrol işlemlerini kapsar.

**Ne Yapar:** Servislerin sağlık durumunu kontrol eder, sağlık kontrollerini yapar, servis durumunu izler, sağlık raporları oluşturur ve servis erişilebilirliğini garanti eder.

### Healthcheck Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost/"]
      interval: 30s
      timeout: 10s
      retries: 3
      start_period: 40s
  
  db:
    image: postgres:13
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres"]
      interval: 10s
      timeout: 5s
      retries: 5
```

### Healthcheck Komutları
```bash
# Healthcheck durumunu kontrol et
docker compose ps

# Belirli servisin healthcheck'ini kontrol et
docker compose ps web

# Healthcheck loglarını göster
docker compose logs web | grep healthcheck

# Healthcheck durumunu detaylı göster
docker compose ps --format "table {{.Name}}\t{{.Status}}\t{{.Health}}"
```

---

## 60. Docker Compose Depends On

**Ne İşe Yarar:** Docker Compose ile servisler arası bağımlılıkları yönetmek için kullanılan depends_on sistemini öğretir. Servis başlatma sırası ve bağımlılık yönetimini kapsar.

**Ne Yapar:** Servislerin başlatma sırasını belirler, bağımlılıkları yönetir, servis hazırlığını kontrol eder, başlatma süreçlerini optimize eder ve servis erişilebilirliğini garanti eder.

### Depends On Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    depends_on:
      db:
        condition: service_healthy
      redis:
        condition: service_started
  
  db:
    image: postgres:13
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres"]
      interval: 10s
      timeout: 5s
      retries: 5
  
  redis:
    image: redis:alpine
    healthcheck:
      test: ["CMD", "redis-cli", "ping"]
      interval: 10s
      timeout: 5s
      retries: 3
```

### Depends On Stratejileri
```bash
# Bağımlılık durumunu kontrol et
docker compose config --services

# Bağımlılık ağacını göster
docker compose config --resolve-image-digests

# Bağımlılık ile başlat
docker compose up --abort-on-container-exit

# Bağımlılık sırasını göster
docker compose up --dry-run
```

---

## 61. Docker Compose Environment

**Ne İşe Yarar:** Docker Compose ile servislerin environment variable'larını yönetmek için kullanılan environment sistemini öğretir. Ortam değişkenleri ve yapılandırma yönetimini kapsar.

**Ne Yapar:** Servislerin environment variable'larını tanımlar, ortam bazlı yapılandırma sağlar, güvenli değişken yönetimi yapar, yapılandırma esnekliği sunar ve ortam izolasyonu sağlar.

### Environment Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    environment:
      - NODE_ENV=production
      - DATABASE_URL=postgresql://user:pass@db:5432/myapp
      - REDIS_URL=redis://redis:6379
      - API_KEY=${API_KEY}
      - DEBUG=false
  
  db:
    image: postgres:13
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: user
      POSTGRES_PASSWORD: ${DB_PASSWORD}
      POSTGRES_INITDB_ARGS: "--encoding=UTF-8"
```

### Environment Yönetimi
```bash
# Environment variable'ları göster
docker compose config --variables

# Belirli servisin environment'ını göster
docker compose exec web env

# Environment variable'ları override et
docker compose up -e DEBUG=true

# .env dosyası kullan
docker compose --env-file .env.prod up
```

---

## 62. Docker Compose Env File

**Ne İşe Yarar:** Docker Compose ile environment variable'larını dosyalardan yüklemek için kullanılan env file sistemini öğretir. Ortam değişkeni dosyaları ve yönetimini kapsar.

**Ne Yapar:** Environment variable'larını dosyalardan yükler, ortam bazlı yapılandırma sağlar, güvenli değişken yönetimi yapar, yapılandırma esnekliği sunar ve ortam izolasyonu sağlar.

### Env File Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    env_file:
      - .env
      - .env.local
      - .env.production
    environment:
      - NODE_ENV=production
  
  db:
    image: postgres:13
    env_file:
      - .env.db
```

### Env File Örnekleri
```bash
# .env dosyası
NODE_ENV=production
DATABASE_URL=postgresql://user:pass@db:5432/myapp
REDIS_URL=redis://redis:6379
API_KEY=your-api-key
DEBUG=false

# .env.local dosyası
DEBUG=true
LOG_LEVEL=debug
```

### Env File Kullanımı
```bash
# Belirli env file ile çalıştır
docker compose --env-file .env.prod up

# Birden fazla env file
docker compose --env-file .env --env-file .env.local up

# Env file'ı doğrula
docker compose config --env-file .env

# Env file değişkenlerini göster
docker compose config --variables
```

---

## 63. Docker Compose Labels

**Ne İşe Yarar:** Docker Compose ile servislerin metadata'larını yönetmek için kullanılan labels sistemini öğretir. Servis etiketleme ve metadata yönetimini kapsar.

**Ne Yapar:** Servislerin metadata'larını tanımlar, servis kategorizasyonu sağlar, otomasyon için etiketler ekler, servis yönetimini kolaylaştırır ve servis izleme sağlar.

### Labels Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    labels:
      - "com.example.description=Web server"
      - "com.example.department=engineering"
      - "com.example.version=1.0"
      - "traefik.enable=true"
      - "traefik.http.routers.web.rule=Host(`example.com`)"
  
  db:
    image: postgres:13
    labels:
      - "com.example.description=Database server"
      - "com.example.department=engineering"
      - "com.example.backup=true"
```

### Labels Kullanımı
```bash
# Labels'ları göster
docker compose config --services

# Belirli label'ı filtrele
docker compose ps --filter "label=com.example.department=engineering"

# Label'ları inspect et
docker compose exec web cat /proc/1/label

# Label'ları güncelle
docker compose up --label-add "com.example.environment=production"
```

---

## 64. Docker Compose Annotations

**Ne İşe Yarar:** Docker Compose ile servislerin ek açıklamalarını yönetmek için kullanılan annotations sistemini öğretir. Servis dokümantasyonu ve açıklama yönetimini kapsar.

**Ne Yapar:** Servislerin açıklamalarını tanımlar, servis dokümantasyonu sağlar, servis bilgilerini organize eder, servis yönetimini kolaylaştırır ve servis izleme sağlar.

### Annotations Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    annotations:
      - "com.example.description=Main web application server"
      - "com.example.owner=engineering-team"
      - "com.example.contact=dev@example.com"
      - "com.example.documentation=https://docs.example.com/web"
      - "com.example.monitoring=prometheus"
  
  db:
    image: postgres:13
    annotations:
      - "com.example.description=Primary database server"
      - "com.example.owner=database-team"
      - "com.example.backup-schedule=daily"
      - "com.example.retention-policy=30-days"
```

### Annotations Kullanımı
```bash
# Annotations'ları göster
docker compose config --services

# Belirli annotation'ı filtrele
docker compose ps --filter "annotation=com.example.owner=engineering-team"

# Annotation'ları inspect et
docker compose exec web cat /proc/1/annotation

# Annotation'ları güncelle
docker compose up --annotation-add "com.example.environment=staging"
```

---

## 65. Docker Compose Deploy

**Ne İşe Yarar:** Docker Compose ile servislerin deployment stratejilerini yönetmek için kullanılan deploy sistemini öğretir. Production deployment ve servis yönetimini kapsar.

**Ne Yapar:** Servislerin deployment stratejilerini tanımlar, rolling update'leri yönetir, servis replikalarını kontrol eder, kaynak limitlerini ayarlar ve deployment süreçlerini otomatikleştirir.

### Deploy Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      replicas: 3
      update_config:
        parallelism: 1
        delay: 10s
        order: start-first
        failure_action: rollback
        monitor: 60s
        max_failure_ratio: 0.3
      restart_policy:
        condition: on-failure
        delay: 5s
        max_attempts: 3
        window: 120s
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
        reservations:
          cpus: '0.25'
          memory: 256M
      placement:
        constraints:
          - node.role == worker
        preferences:
          - spread: node.labels.zone
```

### Deploy Komutları
```bash
# Servisleri deploy et
docker compose deploy

# Belirli servisi deploy et
docker compose deploy web

# Deploy durumunu kontrol et
docker compose ps

# Deploy loglarını göster
docker compose logs

# Deploy geçmişini göster
docker compose ps --format "table {{.Name}}\t{{.Status}}\t{{.CreatedAt}}"
```

---

## 66. Docker Compose Resources

**Ne İşe Yarar:** Docker Compose ile servislerin kaynak kullanımını yönetmek için kullanılan resources sistemini öğretir. CPU, memory ve diğer kaynak limitlerini kapsar.

**Ne Yapar:** Servislerin kaynak kullanımını sınırlar, kaynak tahsisi yapar, performansı optimize eder, kaynak çakışmalarını önler ve sistem kaynaklarını verimli kullanır.

### Resources Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
          pids: 100
        reservations:
          cpus: '0.25'
          memory: 256M
          devices:
            - driver: nvidia
              count: 1
              capabilities: [gpu]
  
  db:
    image: postgres:13
    deploy:
      resources:
        limits:
          cpus: '1.0'
          memory: 1G
        reservations:
          cpus: '0.5'
          memory: 512M
```

### Resources Yönetimi
```bash
# Kaynak kullanımını izle
docker compose stats

# Belirli servisin kaynak kullanımını izle
docker compose stats web

# Kaynak limitlerini kontrol et
docker compose exec web cat /sys/fs/cgroup/cpu/cpu.cfs_quota_us

# Memory kullanımını kontrol et
docker compose exec web cat /sys/fs/cgroup/memory/memory.usage_in_bytes
```

---

## 67. Docker Compose Restart Policy

**Ne İşe Yarar:** Docker Compose ile servislerin yeniden başlatma politikalarını yönetmek için kullanılan restart policy sistemini öğretir. Servis dayanıklılığı ve otomatik yeniden başlatma işlemlerini kapsar.

**Ne Yapar:** Servislerin yeniden başlatma davranışını tanımlar, hata durumlarında otomatik kurtarma sağlar, servis dayanıklılığını artırır, sistem kararlılığını korur ve kesintisiz hizmet sağlar.

### Restart Policy Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    restart: unless-stopped
    deploy:
      restart_policy:
        condition: on-failure
        delay: 5s
        max_attempts: 3
        window: 120s
  
  db:
    image: postgres:13
    restart: always
    deploy:
      restart_policy:
        condition: any
        delay: 10s
        max_attempts: 5
        window: 300s
  
  cache:
    image: redis:alpine
    restart: no
```

### Restart Policy Türleri
```bash
# no: Yeniden başlatma yok
restart: no

# always: Her zaman yeniden başlat
restart: always

# on-failure: Sadece hata durumunda yeniden başlat
restart: on-failure

# unless-stopped: Manuel durdurma hariç yeniden başlat
restart: unless-stopped
```

---

## 68. Docker Compose Update Config

**Ne İşe Yarar:** Docker Compose ile servis güncellemelerini yönetmek için kullanılan update config sistemini öğretir. Rolling update'ler ve güncelleme stratejilerini kapsar.

**Ne Yapar:** Servis güncellemelerini yönetir, rolling update'leri kontrol eder, güncelleme süreçlerini optimize eder, kesintisiz güncelleme sağlar ve güncelleme güvenliğini garanti eder.

### Update Config Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      update_config:
        parallelism: 2
        delay: 10s
        order: start-first
        failure_action: rollback
        monitor: 60s
        max_failure_ratio: 0.3
        start_first: true
  
  api:
    image: myapp:latest
    deploy:
      update_config:
        parallelism: 1
        delay: 30s
        order: stop-first
        failure_action: pause
        monitor: 120s
        max_failure_ratio: 0.1
```

### Update Stratejileri
```bash
# Rolling update başlat
docker compose up -d --force-recreate

# Belirli servisi güncelle
docker compose up -d --force-recreate web

# Güncelleme durumunu izle
docker compose ps

# Güncelleme loglarını göster
docker compose logs -f

# Güncelleme geçmişini kontrol et
docker compose ps --format "table {{.Name}}\t{{.Status}}\t{{.CreatedAt}}"
```

---

## 69. Docker Compose Rollback Config

**Ne İşe Yarar:** Docker Compose ile servis güncellemelerini geri almak için kullanılan rollback config sistemini öğretir. Güncelleme geri alma ve hata kurtarma işlemlerini kapsar.

**Ne Yapar:** Başarısız güncellemeleri geri alır, önceki versiyonlara döner, hata kurtarma sağlar, sistem kararlılığını korur ve güvenli güncelleme süreçleri sağlar.

### Rollback Config Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      update_config:
        parallelism: 1
        delay: 10s
        failure_action: rollback
        monitor: 60s
        max_failure_ratio: 0.3
      rollback_config:
        parallelism: 1
        delay: 5s
        failure_action: pause
        monitor: 30s
        max_failure_ratio: 0.1
        order: stop-first
  
  api:
    image: myapp:latest
    deploy:
      update_config:
        failure_action: rollback
      rollback_config:
        parallelism: 0
        delay: 10s
        order: start-first
```

### Rollback Komutları
```bash
# Manuel rollback başlat
docker compose rollback

# Belirli servisi rollback et
docker compose rollback web

# Rollback durumunu izle
docker compose ps

# Rollback loglarını göster
docker compose logs -f

# Rollback geçmişini kontrol et
docker compose ps --format "table {{.Name}}\t{{.Status}}\t{{.CreatedAt}}"
```

---

## 70. Docker Compose Placement

**Ne İşe Yarar:** Docker Compose ile servislerin hangi node'larda çalışacağını yönetmek için kullanılan placement sistemini öğretir. Node seçimi ve yerleştirme stratejilerini kapsar.

**Ne Yapar:** Servislerin node yerleştirmesini kontrol eder, kaynak optimizasyonu sağlar, yük dengelemesi yapar, node kısıtlamalarını uygular ve yerleştirme stratejilerini yönetir.

### Placement Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      replicas: 3
      placement:
        constraints:
          - node.role == worker
          - node.labels.zone == us-east-1
          - node.labels.environment == production
        preferences:
          - spread: node.labels.zone
          - spread: node.labels.rack
          - spread: node.labels.datacenter
        max_replicas_per_node: 1
  
  db:
    image: postgres:13
    deploy:
      replicas: 1
      placement:
        constraints:
          - node.role == manager
          - node.labels.storage == ssd
          - node.labels.datacenter == us-east-1
        preferences:
          - spread: node.labels.datacenter
```

### Placement Stratejileri
```bash
# Node kısıtlamalarını kontrol et
docker node ls --format "table {{.Hostname}}\t{{.Status}}\t{{.Availability}}\t{{.ManagerStatus}}"

# Node etiketlerini göster
docker node inspect self --format '{{.Spec.Labels}}'

# Servis yerleştirmesini kontrol et
docker compose ps

# Placement durumunu izle
docker compose ps --format "table {{.Name}}\t{{.Node}}\t{{.Status}}"
```

---

## 71. Docker Compose Constraints

**Ne İşe Yarar:** Docker Compose ile servislerin hangi node'larda çalışabileceğini kısıtlamak için kullanılan constraints sistemini öğretir. Node kısıtlamaları ve yerleştirme kurallarını kapsar.

**Ne Yapar:** Servislerin node yerleştirmesini kısıtlar, belirli node'larda çalışmasını zorunlu kılar, kaynak gereksinimlerini kontrol eder, güvenlik politikalarını uygular ve yerleştirme kurallarını yönetir.

### Constraints Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      placement:
        constraints:
          - node.role == worker
          - node.labels.environment == production
          - node.labels.zone == us-east-1
          - node.labels.storage == ssd
          - node.labels.cpu == x86_64
  
  db:
    image: postgres:13
    deploy:
      placement:
        constraints:
          - node.role == manager
          - node.labels.backup == enabled
          - node.labels.memory >= 8GB
          - node.labels.cpu >= 4
```

### Constraints Türleri
```bash
# Node rolü kısıtlaması
- node.role == worker

# Node etiketi kısıtlaması
- node.labels.environment == production

# Node özelliği kısıtlaması
- node.labels.storage == ssd

# Node kapasitesi kısıtlaması
- node.labels.memory >= 8GB

# Node mimarisi kısıtlaması
- node.labels.cpu == x86_64
```

---

## 72. Docker Compose Preferences

**Ne İşe Yarar:** Docker Compose ile servislerin tercih edilen node'larda çalışmasını sağlamak için kullanılan preferences sistemini öğretir. Yerleştirme tercihleri ve dağıtım stratejilerini kapsar.

**Ne Yapar:** Servislerin tercih edilen node'larda çalışmasını sağlar, yük dengelemesi yapar, kaynak optimizasyonu sağlar, yerleştirme tercihlerini yönetir ve dağıtım stratejilerini uygular.

### Preferences Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      replicas: 3
      placement:
        preferences:
          - spread: node.labels.zone
          - spread: node.labels.rack
          - spread: node.labels.datacenter
  
  api:
    image: myapp:latest
    deploy:
      replicas: 2
      placement:
        preferences:
          - spread: node.labels.environment
          - spread: node.labels.availability-zone
```

### Preferences Stratejileri
```bash
# Zone bazlı dağıtım
- spread: node.labels.zone

# Rack bazlı dağıtım
- spread: node.labels.rack

# Datacenter bazlı dağıtım
- spread: node.labels.datacenter

# Environment bazlı dağıtım
- spread: node.labels.environment
```

---

## 73. Docker Compose Replicas

**Ne İşe Yarar:** Docker Compose ile servis replika sayısını yönetmek için kullanılan replicas sistemini öğretir. Servis ölçeklendirme ve replika yönetimini kapsar.

**Ne Yapar:** Servis replika sayısını belirler, otomatik ölçeklendirme sağlar, yük dengelemesi yapar, yüksek erişilebilirlik sunar ve servis kapasitesini yönetir.

### Replicas Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      replicas: 3
      update_config:
        parallelism: 1
        delay: 10s
      restart_policy:
        condition: on-failure
  
  api:
    image: myapp:latest
    deploy:
      replicas: 5
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
  
  db:
    image: postgres:13
    deploy:
      replicas: 1
      placement:
        constraints:
          - node.role == manager
```

### Replicas Yönetimi
```bash
# Replica sayısını değiştir
docker compose up --scale web=5

# Replica durumunu kontrol et
docker compose ps

# Replica loglarını göster
docker compose logs web

# Replica dağılımını kontrol et
docker compose ps --format "table {{.Name}}\t{{.Node}}\t{{.Status}}"
```

---

## 74. Docker Compose Endpoint Mode

**Ne İşe Yarar:** Docker Compose ile servis endpoint'lerinin nasıl yönetileceğini belirlemek için kullanılan endpoint mode sistemini öğretir. Servis erişimi ve endpoint yönetimini kapsar.

**Ne Yapar:** Servis endpoint'lerinin davranışını belirler, load balancing stratejilerini uygular, servis discovery sağlar, endpoint erişimini kontrol eder ve network trafiğini yönetir.

### Endpoint Mode Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    deploy:
      endpoint_mode: dnsrr
      replicas: 3
  
  api:
    image: myapp:latest
    deploy:
      endpoint_mode: vip
      replicas: 2
  
  db:
    image: postgres:13
    deploy:
      endpoint_mode: dnsrr
      replicas: 1
```

### Endpoint Mode Türleri
```bash
# VIP (Virtual IP) mode
endpoint_mode: vip

# DNS Round Robin mode
endpoint_mode: dnsrr
```

---

## 75. Docker Compose Ports

**Ne İşe Yarar:** Docker Compose ile servislerin port mapping'lerini yönetmek için kullanılan ports sistemini öğretir. Port yapılandırması ve erişim kontrolünü kapsar.

**Ne Yapar:** Servislerin port mapping'lerini tanımlar, port erişimini kontrol eder, load balancing sağlar, port güvenliğini yönetir ve network trafiğini yönlendirir.

### Ports Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    ports:
      - "80:80"
      - "443:443"
      - "8080:80"
      - "127.0.0.1:3000:3000"
  
  api:
    image: myapp:latest
    ports:
      - target: 3000
        published: 3000
        protocol: tcp
        mode: host
      - target: 3001
        published: 3001
        protocol: tcp
        mode: ingress
```

### Port Mapping Türleri
```bash
# Basit port mapping
- "80:80"

# IP bazlı port mapping
- "127.0.0.1:3000:3000"

# Detaylı port mapping
- target: 3000
  published: 3000
  protocol: tcp
  mode: host
```

---

## 76. Docker Compose Expose

**Ne İşe Yarar:** Docker Compose ile servislerin hangi port'ları dinleyeceğini belirtmek için kullanılan expose sistemini öğretir. Port dokümantasyonu ve servis iletişimini kapsar.

**Ne Yapar:** Servislerin dinlediği port'ları belirtir, port dokümantasyonu sağlar, servis iletişimini kolaylaştırır, port bilgilerini organize eder ve servis discovery'i destekler.

### Expose Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    expose:
      - "80"
      - "443"
  
  api:
    image: myapp:latest
    expose:
      - "3000"
      - "3001"
  
  db:
    image: postgres:13
    expose:
      - "5432"
```

### Expose vs Ports
```bash
# Expose: Sadece dokümantasyon
expose:
  - "80"

# Ports: Gerçek port mapping
ports:
  - "80:80"
```

---

## 77. Docker Compose Links

**Ne İşe Yarar:** Docker Compose ile servisler arası bağlantıları yönetmek için kullanılan links sistemini öğretir. Servis iletişimi ve bağımlılık yönetimini kapsar.

**Ne Yapar:** Servisler arası bağlantıları tanımlar, servis discovery sağlar, network iletişimini kolaylaştırır, bağımlılıkları yönetir ve servis erişilebilirliğini sağlar.

### Links Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    links:
      - api:backend
      - db:database
  
  api:
    image: myapp:latest
    links:
      - db:database
  
  db:
    image: postgres:13
```

### Links Kullanımı
```bash
# Servis adı ile erişim
curl http://api:3000

# Alias ile erişim
curl http://backend:3000

# Database erişimi
psql -h database -U user -d myapp
```

---

## 78. Docker Compose External Links

**Ne İşe Yarar:** Docker Compose ile dış servislere bağlantı kurmak için kullanılan external links sistemini öğretir. Dış servis entegrasyonu ve bağlantı yönetimini kapsar.

**Ne Yapar:** Dış servislere bağlantı kurar, harici sistemlerle entegrasyon sağlar, servis discovery'i genişletir, dış bağımlılıkları yönetir ve sistem entegrasyonunu kolaylaştırır.

### External Links Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    external_links:
      - redis_standalone:redis
      - mysql_external:mysql
      - legacy_app:legacy
  
  api:
    image: myapp:latest
    external_links:
      - external_api:api
      - external_db:database
```

### External Links Kullanımı
```bash
# Dış Redis'e bağlan
redis-cli -h redis -p 6379

# Dış MySQL'e bağlan
mysql -h mysql -u user -p

# Dış API'ye istek gönder
curl http://api:8080/health
```

---

## 79. Docker Compose Extra Hosts

**Ne İşe Yarar:** Docker Compose ile container'lara ek host kayıtları eklemek için kullanılan extra hosts sistemini öğretir. Host mapping ve DNS yönetimini kapsar.

**Ne Yapar:** Container'lara ek host kayıtları ekler, DNS çözümlemesini özelleştirir, host mapping sağlar, network erişimini kolaylaştırır ve DNS yönetimini yapar.

### Extra Hosts Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    extra_hosts:
      - "api.example.com:192.168.1.100"
      - "db.example.com:192.168.1.101"
      - "cache.example.com:192.168.1.102"
  
  api:
    image: myapp:latest
    extra_hosts:
      - "external-api.com:10.0.0.50"
      - "monitoring.com:10.0.0.51"
```

### Extra Hosts Kullanımı
```bash
# Host kayıtlarını kontrol et
docker compose exec web cat /etc/hosts

# Host erişimini test et
docker compose exec web ping api.example.com

# DNS çözümlemesini test et
docker compose exec web nslookup db.example.com
```

---

## 80. Docker Compose DNS

**Ne İşe Yarar:** Docker Compose ile container'ların DNS ayarlarını yönetmek için kullanılan DNS sistemini öğretir. DNS sunucuları ve çözümleme ayarlarını kapsar.

**Ne Yapar:** Container'ların DNS sunucularını belirler, DNS çözümlemesini yönetir, DNS ayarlarını özelleştirir, network erişimini sağlar ve DNS güvenliğini yönetir.

### DNS Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    dns:
      - 8.8.8.8
      - 8.8.4.4
      - 1.1.1.1
  
  api:
    image: myapp:latest
    dns:
      - 192.168.1.1
      - 10.0.0.1
```

### DNS Yönetimi
```bash
# DNS ayarlarını kontrol et
docker compose exec web cat /etc/resolv.conf

# DNS çözümlemesini test et
docker compose exec web nslookup google.com

# DNS sunucularını test et
docker compose exec web dig @8.8.8.8 google.com
```

---

## 81. Docker Compose DNS Search

**Ne İşe Yarar:** Docker Compose ile container'ların DNS arama domain'lerini yönetmek için kullanılan DNS search sistemini öğretir. DNS arama yolları ve domain çözümlemesini kapsar.

**Ne Yapar:** Container'ların DNS arama domain'lerini belirler, domain çözümlemesini kolaylaştırır, DNS arama yollarını yönetir, network erişimini iyileştirir ve DNS yapılandırmasını optimize eder.

### DNS Search Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    dns_search:
      - example.com
      - internal.example.com
      - dev.example.com
  
  api:
    image: myapp:latest
    dns_search:
      - api.example.com
      - services.example.com
```

### DNS Search Kullanımı
```bash
# DNS arama ayarlarını kontrol et
docker compose exec web cat /etc/resolv.conf

# Kısa domain ile erişim
docker compose exec web ping api

# DNS arama yollarını test et
docker compose exec web nslookup web
```

---

## 82. Docker Compose DNS Options

**Ne İşe Yarar:** Docker Compose ile container'ların DNS davranışını özelleştirmek için kullanılan DNS options sistemini öğretir. DNS ayarları ve davranış kontrolünü kapsar.

**Ne Yapar:** DNS davranışını özelleştirir, DNS ayarlarını kontrol eder, DNS performansını optimize eder, DNS güvenliğini artırır ve DNS yapılandırmasını yönetir.

### DNS Options Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    dns_opt:
      - timeout:2
      - attempts:3
      - ndots:1
      - use-vc
  
  api:
    image: myapp:latest
    dns_opt:
      - timeout:5
      - attempts:5
      - ndots:2
```

### DNS Options Türleri
```bash
# Timeout ayarı
timeout:2

# Deneme sayısı
attempts:3

# Nokta sayısı
ndots:1

# TCP kullanımı
use-vc
```

---

## 83. Docker Compose Hostname

**Ne İşe Yarar:** Docker Compose ile container'ların hostname'lerini yönetmek için kullanılan hostname sistemini öğretir. Container kimliği ve network erişimini kapsar.

**Ne Yapar:** Container'ların hostname'lerini belirler, network erişimini kolaylaştırır, container kimliğini yönetir, servis discovery'i destekler ve network yapılandırmasını organize eder.

### Hostname Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    hostname: web-server
    container_name: web-container
  
  api:
    image: myapp:latest
    hostname: api-server
    container_name: api-container
  
  db:
    image: postgres:13
    hostname: db-server
    container_name: db-container
```

### Hostname Kullanımı
```bash
# Hostname'i kontrol et
docker compose exec web hostname

# Hostname ile erişim
docker compose exec api ping web-server

# Container adı ile erişim
docker compose exec web ping api-container
```

---

## 84. Docker Compose Domainname

**Ne İşe Yarar:** Docker Compose ile container'ların domain adlarını yönetmek için kullanılan domainname sistemini öğretir. Domain yapılandırması ve network organizasyonunu kapsar.

**Ne Yapar:** Container'ların domain adlarını belirler, network organizasyonunu sağlar, domain yapılandırmasını yönetir, servis discovery'i destekler ve network yapısını organize eder.

### Domainname Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    hostname: web
    domainname: example.com
  
  api:
    image: myapp:latest
    hostname: api
    domainname: services.example.com
  
  db:
    image: postgres:13
    hostname: db
    domainname: data.example.com
```

### Domainname Kullanımı
```bash
# Tam domain adını kontrol et
docker compose exec web hostname -f

# Domain ile erişim
docker compose exec api ping web.example.com

# DNS çözümlemesini test et
docker compose exec web nslookup api.services.example.com
```

---

## 85. Docker Compose Mac Address

**Ne İşe Yarar:** Docker Compose ile container'ların MAC adreslerini yönetmek için kullanılan mac address sistemini öğretir. Network kimliği ve MAC adresi kontrolünü kapsar.

**Ne Yapar:** Container'ların MAC adreslerini belirler, network kimliğini kontrol eder, MAC adresi yönetimini sağlar, network güvenliğini artırır ve network yapılandırmasını organize eder.

### Mac Address Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    mac_address: "02:42:ac:11:00:02"
  
  api:
    image: myapp:latest
    mac_address: "02:42:ac:11:00:03"
  
  db:
    image: postgres:13
    mac_address: "02:42:ac:11:00:04"
```

### Mac Address Yönetimi
```bash
# MAC adresini kontrol et
docker compose exec web ip link show

# Network interface bilgilerini göster
docker compose exec web ip addr show

# MAC adresi ile filtreleme
docker compose ps --filter "label=com.docker.compose.service=web"
```

---

## 86. Docker Compose Init

**Ne İşe Yarar:** Docker Compose ile container'ların init sistemini yönetmek için kullanılan init sistemini öğretir. Process yönetimi ve zombie process temizliğini kapsar.

**Ne Yapar:** Container'larda init sistemi çalıştırır, zombie process'leri temizler, signal handling sağlar, process yönetimini iyileştirir ve container yaşam döngüsünü yönetir.

### Init Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    init: true
  
  api:
    image: myapp:latest
    init: true
  
  db:
    image: postgres:13
    init: false
```

### Init Kullanımı
```bash
# Init process'ini kontrol et
docker compose exec web ps aux

# Process ağacını göster
docker compose exec web pstree

# Zombie process'leri kontrol et
docker compose exec web ps aux | grep Z
```

---

## 87. Docker Compose Tty

**Ne İşe Yarar:** Docker Compose ile container'ların TTY ayarlarını yönetmek için kullanılan TTY sistemini öğretir. Terminal yapılandırması ve interaktif erişimi kapsar.

**Ne Yapar:** Container'larda TTY ayarlarını yapar, terminal yapılandırmasını sağlar, interaktif erişimi kolaylaştırır, terminal davranışını kontrol eder ve kullanıcı deneyimini iyileştirir.

### TTY Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    tty: true
  
  api:
    image: myapp:latest
    tty: false
  
  shell:
    image: ubuntu:latest
    tty: true
    stdin_open: true
```

### TTY Kullanımı
```bash
# TTY ile bağlan
docker compose exec -it web bash

# TTY olmadan bağlan
docker compose exec -T web cat /etc/hosts

# TTY durumunu kontrol et
docker compose exec web tty
```

---

## 88. Docker Compose Stdin Open

**Ne İşe Yarar:** Docker Compose ile container'ların stdin erişimini yönetmek için kullanılan stdin open sistemini öğretir. Standart giriş yapılandırması ve interaktif erişimi kapsar.

**Ne Yapar:** Container'ların stdin erişimini açar, interaktif erişimi sağlar, standart giriş yapılandırmasını yönetir, kullanıcı etkileşimini kolaylaştırır ve terminal deneyimini iyileştirir.

### Stdin Open Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    stdin_open: true
    tty: true
  
  api:
    image: myapp:latest
    stdin_open: false
  
  shell:
    image: ubuntu:latest
    stdin_open: true
    tty: true
```

### Stdin Open Kullanımı
```bash
# Interaktif bağlantı
docker compose exec -it web bash

# Stdin ile komut çalıştır
echo "hello" | docker compose exec -i web cat

# Stdin durumunu kontrol et
docker compose exec web ls -la /proc/1/fd/0
```

---

## 89. Docker Compose Working Dir

**Ne İşe Yarar:** Docker Compose ile container'ların çalışma dizinini yönetmek için kullanılan working dir sistemini öğretir. Çalışma dizini yapılandırması ve dosya erişimini kapsar.

**Ne Yapar:** Container'ların çalışma dizinini belirler, dosya erişimini kolaylaştırır, komut çalıştırma ortamını yönetir, dosya yollarını organize eder ve container içi dosya yapısını düzenler.

### Working Dir Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    working_dir: /var/www/html
    volumes:
      - ./src:/var/www/html
  
  api:
    image: myapp:latest
    working_dir: /app
    volumes:
      - ./api:/app
  
  db:
    image: postgres:13
    working_dir: /var/lib/postgresql/data
    volumes:
      - postgres_data:/var/lib/postgresql/data
```

### Working Dir Kullanımı
```bash
# Çalışma dizinini kontrol et
docker compose exec web pwd

# Çalışma dizinindeki dosyaları listele
docker compose exec web ls -la

# Çalışma dizinini değiştir
docker compose exec -w /tmp web ls -la
```

---

## 90. Docker Compose User

**Ne İşe Yarar:** Docker Compose ile container'ların çalışma kullanıcısını yönetmek için kullanılan user sistemini öğretir. Kullanıcı yönetimi ve güvenlik kontrolünü kapsar.

**Ne Yapar:** Container'ların çalışma kullanıcısını belirler, güvenlik politikalarını uygular, dosya izinlerini yönetir, kullanıcı kimliğini kontrol eder ve güvenli çalışma ortamı sağlar.

### User Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    user: "1000:1000"
    volumes:
      - ./src:/var/www/html
  
  api:
    image: myapp:latest
    user: "node:node"
    volumes:
      - ./api:/app
  
  db:
    image: postgres:13
    user: "postgres:postgres"
    volumes:
      - postgres_data:/var/lib/postgresql/data
```

### User Yönetimi
```bash
# Kullanıcı kimliğini kontrol et
docker compose exec web id

# Kullanıcı bilgilerini göster
docker compose exec web whoami

# Dosya izinlerini kontrol et
docker compose exec web ls -la /var/www/html

# Kullanıcı değiştir
docker compose exec -u root web bash
```

---

## 91. Docker Compose Capabilities

**Ne İşe Yarar:** Docker Compose ile container'ların Linux capabilities'lerini yönetmek için kullanılan capabilities sistemini öğretir. Güvenlik izinleri ve sistem yetkilerini kapsar.

**Ne Yapar:** Container'ların Linux capabilities'lerini belirler, güvenlik izinlerini kontrol eder, sistem yetkilerini yönetir, güvenlik politikalarını uygular ve container güvenliğini artırır.

### Capabilities Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    cap_add:
      - CHOWN
      - SETGID
      - SETUID
    cap_drop:
      - ALL
  
  api:
    image: myapp:latest
    cap_add:
      - NET_ADMIN
      - SYS_ADMIN
    cap_drop:
      - MKNOD
      - SYS_CHROOT
  
  db:
    image: postgres:13
    cap_add:
      - SYS_PTRACE
    cap_drop:
      - ALL
```

### Capabilities Yönetimi
```bash
# Mevcut capabilities'leri kontrol et
docker compose exec web cat /proc/1/status | grep Cap

# Capabilities'leri listele
docker compose exec web capsh --print

# Güvenlik durumunu kontrol et
docker compose exec web id
```

---

## 92. Docker Compose Security Opt

**Ne İşe Yarar:** Docker Compose ile container'ların güvenlik seçeneklerini yönetmek için kullanılan security opt sistemini öğretir. Güvenlik politikaları ve erişim kontrolünü kapsar.

**Ne Yapar:** Container'ların güvenlik seçeneklerini belirler, güvenlik politikalarını uygular, erişim kontrolünü sağlar, güvenlik izinlerini yönetir ve container güvenliğini artırır.

### Security Opt Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    security_opt:
      - no-new-privileges:true
      - seccomp:unconfined
  
  api:
    image: myapp:latest
    security_opt:
      - apparmor:docker-default
      - label:user:USER
      - label:role:ROLE
  
  db:
    image: postgres:13
    security_opt:
      - no-new-privileges:true
      - seccomp:default
```

### Security Opt Türleri
```bash
# Yeni ayrıcalık yok
no-new-privileges:true

# Seccomp profili
seccomp:unconfined

# AppArmor profili
apparmor:docker-default

# SELinux etiketleri
label:user:USER
label:role:ROLE
```

---

## 93. Docker Compose Read Only

**Ne İşe Yarar:** Docker Compose ile container'ların dosya sistemini salt okunur yapmak için kullanılan read only sistemini öğretir. Dosya sistemi güvenliği ve değişiklik korumasını kapsar.

**Ne Yapar:** Container'ların dosya sistemini salt okunur yapar, dosya değişikliklerini engeller, güvenlik seviyesini artırır, dosya sistemi bütünlüğünü korur ve container güvenliğini sağlar.

### Read Only Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    read_only: true
    tmpfs:
      - /tmp
      - /var/cache/nginx
      - /var/run
    volumes:
      - ./config:/etc/nginx/conf.d:ro
  
  api:
    image: myapp:latest
    read_only: true
    tmpfs:
      - /tmp
      - /var/log
    volumes:
      - ./logs:/var/log:rw
  
  db:
    image: postgres:13
    read_only: false
    volumes:
      - postgres_data:/var/lib/postgresql/data
```

### Read Only Kullanımı
```bash
# Dosya sistemi durumunu kontrol et
docker compose exec web mount | grep "ro,"

# Yazma izinlerini test et
docker compose exec web touch /test.txt

# Geçici dosya sistemi kullanımı
docker compose exec web ls -la /tmp
```

---

## 94. Docker Compose Tmpfs

**Ne İşe Yarar:** Docker Compose ile container'lara geçici dosya sistemleri bağlamak için kullanılan tmpfs sistemini öğretir. Geçici depolama ve performans optimizasyonunu kapsar.

**Ne Yapar:** Container'lara geçici dosya sistemleri bağlar, RAM tabanlı depolama sağlar, performansı artırır, geçici verileri yönetir ve disk I/O'yu azaltır.

### Tmpfs Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    tmpfs:
      - /tmp
      - /var/cache/nginx:100m
      - /var/run:50m
      - /var/log:200m
  
  api:
    image: myapp:latest
    tmpfs:
      - /tmp:100m,noexec,nosuid,size=100m
      - /var/cache:50m
      - /tmp/uploads:200m
  
  cache:
    image: redis:alpine
    tmpfs:
      - /data:1g
```

### Tmpfs Seçenekleri
```bash
# Boyut belirtme
/tmp:100m

# Güvenlik seçenekleri
/tmp:100m,noexec,nosuid

# Sadece yol
/tmp

# Boyut ve seçenekler
/var/cache:50m,noexec
```

---

## 95. Docker Compose Oom Score Adj

**Ne İşe Yarar:** Docker Compose ile container'ların OOM (Out of Memory) skorunu yönetmek için kullanılan oom score adj sistemini öğretir. Bellek yönetimi ve öncelik kontrolünü kapsar.

**Ne Yapar:** Container'ların OOM skorunu belirler, bellek yönetimini kontrol eder, process önceliğini ayarlar, sistem kaynaklarını optimize eder ve bellek güvenliğini sağlar.

### OOM Score Adj Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    oom_score_adj: 1000
    deploy:
      resources:
        limits:
          memory: 512M
  
  api:
    image: myapp:latest
    oom_score_adj: 500
    deploy:
      resources:
        limits:
          memory: 1G
  
  db:
    image: postgres:13
    oom_score_adj: -100
    deploy:
      resources:
        limits:
          memory: 2G
```

### OOM Score Adj Değerleri
```bash
# Yüksek öncelik (düşük skor)
oom_score_adj: -100

# Normal öncelik
oom_score_adj: 0

# Düşük öncelik (yüksek skor)
oom_score_adj: 1000

# OOM skorunu kontrol et
docker compose exec web cat /proc/1/oom_score_adj
```

---

## 96. Docker Compose Pid

**Ne İşe Yarar:** Docker Compose ile container'ların PID namespace'ini yönetmek için kullanılan pid sistemini öğretir. Process namespace'i ve izolasyon kontrolünü kapsar.

**Ne Yapar:** Container'ların PID namespace'ini belirler, process izolasyonunu kontrol eder, host process'lerine erişimi yönetir, güvenlik seviyesini ayarlar ve process yönetimini optimize eder.

### PID Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    pid: host
  
  api:
    image: myapp:latest
    pid: host
  
  db:
    image: postgres:13
    pid: private
  
  monitoring:
    image: prometheus:latest
    pid: host
    volumes:
      - /proc:/host/proc:ro
```

### PID Namespace Türleri
```bash
# Host PID namespace
pid: host

# Private PID namespace (varsayılan)
pid: private

# PID namespace'i kontrol et
docker compose exec web ps aux

# Host process'lerini görüntüle
docker compose exec web ps -ef
```

---

## 97. Docker Compose Uts

**Ne İşe Yarar:** Docker Compose ile container'ların UTS (Unix Time Sharing) namespace'ini yönetmek için kullanılan uts sistemini öğretir. Hostname ve domain adı izolasyonunu kapsar.

**Ne Yapar:** Container'ların UTS namespace'ini belirler, hostname izolasyonunu kontrol eder, domain adı yönetimini sağlar, sistem kimliğini yönetir ve namespace izolasyonunu optimize eder.

### UTS Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    uts: host
    hostname: web-server
  
  api:
    image: myapp:latest
    uts: private
    hostname: api-server
  
  db:
    image: postgres:13
    uts: private
    hostname: db-server
```

### UTS Namespace Türleri
```bash
# Host UTS namespace
uts: host

# Private UTS namespace (varsayılan)
uts: private

# Hostname'i kontrol et
docker compose exec web hostname

# Domain adını kontrol et
docker compose exec web hostname -f
```

---

## 98. Docker Compose Ipc

**Ne İşe Yarar:** Docker Compose ile container'ların IPC (Inter-Process Communication) namespace'ini yönetmek için kullanılan ipc sistemini öğretir. Process iletişimi ve paylaşılan bellek yönetimini kapsar.

**Ne Yapar:** Container'ların IPC namespace'ini belirler, process iletişimini kontrol eder, paylaşılan bellek yönetimini sağlar, IPC kaynaklarını optimize eder ve process izolasyonunu yönetir.

### IPC Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    ipc: host
  
  api:
    image: myapp:latest
    ipc: private
  
  db:
    image: postgres:13
    ipc: private
  
  cache:
    image: redis:alpine
    ipc: host
```

### IPC Namespace Türleri
```bash
# Host IPC namespace
ipc: host

# Private IPC namespace (varsayılan)
ipc: private

# IPC kaynaklarını kontrol et
docker compose exec web ipcs

# Paylaşılan bellek durumunu kontrol et
docker compose exec web cat /proc/sysvipc/shm
```

---

## 99. Docker Compose Cgroup Parent

**Ne İşe Yarar:** Docker Compose ile container'ların cgroup parent'ını yönetmek için kullanılan cgroup parent sistemini öğretir. Kaynak gruplandırma ve cgroup hiyerarşisini kapsar.

**Ne Yapar:** Container'ların cgroup parent'ını belirler, kaynak gruplandırmasını kontrol eder, cgroup hiyerarşisini yönetir, kaynak izolasyonunu sağlar ve sistem kaynaklarını organize eder.

### Cgroup Parent Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    cgroup_parent: "web.slice"
    deploy:
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
  
  api:
    image: myapp:latest
    cgroup_parent: "api.slice"
    deploy:
      resources:
        limits:
          cpus: '1.0'
          memory: 1G
  
  db:
    image: postgres:13
    cgroup_parent: "db.slice"
    deploy:
      resources:
        limits:
          cpus: '2.0'
          memory: 2G
```

### Cgroup Parent Kullanımı
```bash
# Cgroup hiyerarşisini kontrol et
docker compose exec web cat /proc/1/cgroup

# Cgroup kaynaklarını kontrol et
docker compose exec web cat /sys/fs/cgroup/memory/docker/*/memory.usage_in_bytes

# Cgroup parent'ını kontrol et
systemctl status web.slice
```

---

## 100. Docker Compose Runtime

**Ne İşe Yarar:** Docker Compose ile container'ların runtime'ını yönetmek için kullanılan runtime sistemini öğretir. Container runtime seçimi ve performans optimizasyonunu kapsar.

**Ne Yapar:** Container'ların runtime'ını belirler, performans optimizasyonu sağlar, runtime seçeneklerini yönetir, sistem kaynaklarını optimize eder ve container performansını artırır.

### Runtime Yapılandırması
```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:alpine
    runtime: runc
    deploy:
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
  
  api:
    image: myapp:latest
    runtime: crun
    deploy:
      resources:
        limits:
          cpus: '1.0'
          memory: 1G
  
  db:
    image: postgres:13
    runtime: runc
    deploy:
      resources:
        limits:
          cpus: '2.0'
          memory: 2G
```

### Runtime Türleri
```bash
# Runc runtime (varsayılan)
runtime: runc

# Crun runtime (daha hızlı)
runtime: crun

# Runtime'ı kontrol et
docker compose exec web cat /proc/1/comm

# Runtime performansını test et
docker compose exec web time sleep 1
```

---

Bu Docker cheatsheet, Docker'ın en gelişmiş ve özel özelliklerini kapsar. Her komutun Türkçe açıklaması bulunmaktadır ve production ortamlarında kullanılan tüm teknikleri içerir. Artık 100 kapsamlı bölüm ile Docker'ın tüm özelliklerini detaylı bir şekilde ele alıyoruz!