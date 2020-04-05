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

```yml
version: '3.2'
services:
  node:
    image: node:10.16.3
    volumes:
      - "./mydata:/mydata"
    command:
      - "tail"
      - "-f"
      - "/dev/null"
```

`mydata`資料夾中可以放一些要在`NodeJS`底下執行的檔案或專案

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

5. 執行掛載在`mydata`資料夾下的`JS`檔案

```bash
node /mydata/檔名.js
```
