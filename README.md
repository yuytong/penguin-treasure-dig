# 挖土姬一路挖

手機與桌面瀏覽器皆可遊玩。手機可觸控移動，第二關提供方向挖掘按鈕；桌面版可用滑鼠操作。

本專案是純靜態 HTML5 Canvas 遊戲，Docker 使用 Nginx 提供網頁服務，GitHub Actions 會將 `dist/` 自動發布至 GitHub Pages。

## 本機啟動

需要 Docker Desktop（macOS、Windows）或 Docker Engine（Linux）。在專案根目錄執行：

```sh
./scripts/start.sh
```

預設網址：<http://localhost:8080>。自訂連接埠：

```sh
PORT=3000 ./scripts/start.sh
```

若未安裝 Docker，也可以用 Python 直接提供靜態遊戲檔案：

```sh
python3 -m http.server 8080 --directory dist
```

然後開啟 <http://localhost:8080>；在終端機按 `Ctrl+C` 停止。

## 停止

```sh
./scripts/stop.sh
```

## 常用指令

```sh
docker logs term-dig-game
docker ps
```

可透過 `CONTAINER_NAME=my-game` 自訂容器名稱；啟動與停止時需使用相同值。
