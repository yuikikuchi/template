# Nginx + Tomcat 最小構成

Docker環境における、Nginx + Tomcat の最小構成をテンプレートとしてメモする。

## 1. 構成

### 1.1. 初回構成

```text
.
├── docs
├── nginx
│   ├── Dockerfile
│   └── conf.d
│       └── nginx.conf
├── tomcat
│   ├── Dockerfile
│   └── webapps
│       └── sample
│           └── helloworld.html
└── docker-compose.yml
```

### 1.2. Docker起動後構成

```text
.
├── docs
├── nginx
│   ├── Dockerfile
│   ├── conf.d
│   │   └── nginx.conf
│   └── log
│       ├── access.log
│       ├── error.log
│       ├── tomcat_access.log
│       └── tomcat_error.log
└── tomcat
│   ├── Dockerfile
│   ├── log
│   │   ├── catalina.yyyy-MM-dd.log
│   │   ├── host-manager.yyyy-MM-dd.log
│   │   ├── localhost.yyyy-MM-dd.log
│   │   ├── localhost_access_log.yyyy-MM-dd.txt
│   │   └── manager.yyyy-MM-dd.log
│   └── webapps
│       └── sample
│           └── helloworld.html
└── docker-compose.yml
```

## 2. 実行手順

### 2.1. Imageの作成

```bash
docker-compose build
```

### 2.2. コンテナ起動

```bash
docker-compose up -d
```

### 2.3. 停止と削除

```bash
docker-compose down
```

## ブラウザ表示

```text
http:localhost:80/helloworld.html
```
