像素動物素材放置說明
========================

把你的像素動物素材放進這個資料夾（public/animals/<動物id>/），並在 config.json 登記。
支援四種動物 id：sheep（綿羊）、kitten（小貓）、chicken（白羽雞）、elk（麋鹿）

支援的素材類型（擇一）：
  1) 靜態圖 / GIF   -> 直接放圖片，GIF 會自動播放（當作走路動畫）
     例：public/animals/sheep/walk.gif
     例：public/animals/sheep/walk.png

  2) MP4 走路動畫    -> 地圖標記會用 <video> 播放（模擬走路）
     例：public/animals/sheep/walk.mp4

  3) sprite sheet    -> 一張水平連拍圖，按幀播放
     例：public/animals/sheep/walk-sprite.png （8 格，每格 48x48）

config.json 登記範例（把 null 換成以下任一）：

  {
    "sheep": { "type": "image",  "src": "/animals/sheep/walk.gif" },
    "kitten": { "type": "video",  "src": "/animals/kitten/walk.mp4" },
    "chicken": { "type": "sprite", "src": "/animals/chicken/walk-sprite.png", "frames": 8, "frameW": 48, "frameH": 48 },
    "elk": null
  }

  "thumb" 可另指選擇畫面用的預覽圖（可省略，會用 src）。

沒設定或檔案不存在時，自動退回內建的像素動物（綿羊/小貓/白羽雞/麋鹿），
等你放入素材後，地圖定位圖標就會改用你的檔案。

※ 檔案放好後，重新執行「npm run dev」（或重新建置）即可看到效果。
