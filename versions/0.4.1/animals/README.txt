像素動物素材放置說明
========================

你的素材放在 public/animals/，並在 config.json 登記即可。

目前的動物 id 與對應素材：
  sheep                 -> Sheep/咩咩.png
  kitten                -> Kitty/小貓.png
  chicken（大雞）        -> kitten/大雞.png
  elk                   -> elk/麋鹿.png
  cow（小牛，有走路MP4）  -> Cow/小牛.mp4 + Cow/小牛.png
  leopard（雪豹）        -> Leopard/雪豹.png
  arknights_niandao（年導） -> Arknights/年導.png
  arknights_wangbie（望別） -> Arknights/望別.png

支援類型（在 config.json 的 type 欄位）：
  image  -> 靜態圖 / GIF（GIF 會自動播放）
  video  -> MP4 走路動畫（地圖標記用 <video> 內嵌播放，模擬走路）
  sprite -> 水平連拍圖（frames/frameW/frameH 依幀播放）

新增或替換素材步驟：
  1) 把檔案放到 public/animals/<動物id>/ 下
  2) 編輯 public/animals/config.json 登記 type 與 src
  3) 重新執行 npm run dev（或重新建置）

config.json 格式範例：
  {
    "sheep":  { "type": "image", "src": "/animals/Sheep/咩咩.png" },
    "cow":    { "type": "video", "src": "/animals/Cow/小牛.mp4", "thumb": "/animals/Cow/小牛.png" },
    "chicken": { "type": "sprite", "src": "/animals/kitten/walk-sprite.png", "frames": 8, "frameW": 48, "frameH": 48 }
  }
