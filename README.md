# NodeJS 10.16.3 for docker

## 需求環境

1. docker
2. docker-compose

## 使用說明

### 修改啟動設定檔參數

```bash
cp docker-compose.yml.example docker-compose.yml
```

docker-compose.yml

可以把`mydata`資料夾換成自己的`NodeJS`專案資料夾，例如`myproject`

指定`working_dir`到專案路徑，例如`/myproject`

開放專案需要的`port`，例如`8080`

將`command`修改成專案啟動指令，例如`npm start`

```yml
version: '3.2'
services:
  node:
    image: node:10.16.3
    working_dir: /myproject
    ports:
      - "8080:8080"
    volumes:
      - "./myproject:/myproject"
    command:
      - "npm"
      - "start"
```

### 啟動`NodeJS`

```bash
docker-compose up
```

### 背景啟動`NodeJS`

```bash
docker-compose up -d
```

### 結束`NodeJS`

```bash
docker-compose down
```

### 一些常用的操作指令

1. 查看目前有運行的`docker container`

```bash
docker ps
```

2. 連線到某個`docker container`

```bash
docker exec -it CONTAINER_ID bash
```

--- 以下指令請連線到`docker container`中執行 ---

3. 查看`NodeJS`版本

```bash
node -v
```

4. 查看`npm`版本

```bash
npm -v
```
