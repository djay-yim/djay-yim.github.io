---
title: "Docker Compose 명령어 모음"
permalink: /notes/docker-compose-usecases/
toc: true
toc_sticky: true
categories:
  - notes
tags:
  - docker
  - docker-compose
  - container
---

## #Docker #Compose #Commands

### 🔥 자주 사용하는 Docker Compose 명령어

| 명령어 | 설명 | 주요 옵션 |
|-------|------|----------|
| `docker-compose up` | 컨테이너 생성 및 시작 | `-d` (백그라운드), `--build` (이미지 재빌드) |
| `docker-compose down` | 컨테이너, 네트워크, 볼륨 중지 및 제거 | `--volumes` (볼륨 제거), `--rmi all` (이미지 제거) |
| `docker-compose ps` | 실행 중인 컨테이너 상태 확인 | - |
| `docker-compose logs` | 서비스 로그 확인 | `-f` (실시간 로그), `--tail=10` (마지막 10줄) |
| `docker-compose start/stop` | 컨테이너 시작/중지 (삭제 없음) | - |
| `docker-compose restart` | 실행 중인 서비스 재시작 | - |
| `docker-compose exec` | 실행 중인 컨테이너에서 명령 실행 | - |
| `docker-compose build` | 서비스 이미지 빌드/재빌드 | `--no-cache` (캐시 사용 안함) |

> Docker Compose는 여러 컨테이너를 한번에 관리하기 위한 강력한 도구입니다.
{: .notice--info}

---

## 명령어 상세 설명

### ⭐ docker-compose up
> 컨테이너 생성 및 시작
```shell
# 기본 실행
docker-compose up

# 백그라운드에서 실행
docker-compose up -d

# 이미지 재빌드 후 실행
docker-compose up --build

# 특정 서비스만 시작
docker-compose up -d web db
```

### ⭐ docker-compose down
> 리소스 중지 및 제거
```shell
# 컨테이너와 네트워크 중지 및 제거
docker-compose down

# 컨테이너, 네트워크, 볼륨 모두 제거
docker-compose down --volumes

# 컨테이너, 네트워크, 로컬 이미지 모두 제거
docker-compose down --rmi all
```

### ⭐ docker-compose ps
> 컨테이너 상태 확인
```shell
# 모든 서비스 상태 확인
docker-compose ps

# 특정 서비스 상태만 확인
docker-compose ps web
```

### ⭐ docker-compose logs
> 로그 확인
```shell
# 모든 서비스 로그 확인
docker-compose logs

# 실시간 로그 보기
docker-compose logs -f

# 특정 서비스 로그만 확인
docker-compose logs web

# 마지막 10줄만 확인
docker-compose logs --tail=10
```

### ⭐ docker-compose start/stop
> 컨테이너 시작/중지 (삭제하지 않음)
```shell
# 모든 서비스 시작
docker-compose start

# 모든 서비스 중지
docker-compose stop

# 특정 서비스만 시작/중지
docker-compose start web
docker-compose stop db
```

### ⭐ docker-compose restart
> 서비스 재시작
```shell
# 모든 서비스 재시작
docker-compose restart

# 특정 서비스만 재시작
docker-compose restart web
```

### ⭐ docker-compose exec
> 실행 중인 컨테이너에서 명령 실행
```shell
# 웹 서비스 컨테이너에서 bash 실행
docker-compose exec web bash

# DB 서비스에서 특정 명령 실행
docker-compose exec db psql -U postgres
```

### ⭐ docker-compose build
> 서비스 이미지 빌드/재빌드
```shell
# 모든 서비스 빌드
docker-compose build

# 캐시 없이 빌드
docker-compose build --no-cache

# 특정 서비스만 빌드
docker-compose build web
```

## 추가 유용한 명령어

### ⭐ docker-compose config
> 구성 확인 및 유효성 검사
```shell
# 설정 유효성 검사
docker-compose config

# 서비스 구성 확인
docker-compose config --services
```

### ⭐ docker-compose pull
> 서비스 이미지 가져오기
```shell
# 모든 서비스 이미지 가져오기
docker-compose pull

# 특정 서비스 이미지만 가져오기
docker-compose pull web
```

### ⭐ docker-compose top
> 실행 중인 프로세스 표시
```shell
# 모든 서비스 프로세스 확인
docker-compose top
```

## 🚀 유용한 활용 사례

### 개발 환경 설정
```yaml
# 개발 환경용 docker-compose.yml 예시
version: '3'
services:
  web:
    build: .
    ports:
      - "8000:8000"
    volumes:
      - .:/app
    depends_on:
      - db
  db:
    image: postgres:13
    environment:
      - POSTGRES_PASSWORD=password
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

### 스케일링
```shell
# 웹 서비스를 3개 인스턴스로 스케일링
docker-compose up -d --scale web=3
```

### 프로덕션 vs 개발 설정
```shell
# 개발 환경 (기본 docker-compose.yml 사용)
docker-compose up -d

# 프로덕션 환경 (프로덕션 설정 파일 사용)
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

## 🛬 마무리
> Docker Compose는 복잡한 다중 컨테이너 애플리케이션을 쉽게 관리할 수 있게 해주는 강력한 도구입니다. 이 명령어들을 활용하여 개발 및 배포 워크플로우를 효율적으로 구성해보세요.

## References
- [Docker Compose 공식 문서](https://docs.docker.com/compose/){:target="_blank"}
- [Docker Compose 명령어 참조](https://docs.docker.com/compose/reference/){:target="_blank"}