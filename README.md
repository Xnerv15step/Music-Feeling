# 心情播放器 Mood Player
<img width="1920" height="912" alt="心情播放器 - Google Chrome 2026_2_20 上午 10_48_36" src="https://github.com/user-attachments/assets/f16dd884-7727-4836-b460-2596cb2311c2" />

根據你當下的心情，推薦對應的音樂曲目與搜尋連結。

## 功能

- 五種心情選項：空洞／喪、亢奮／躁動、平靜／飄渺、懷念／憂鬱、煩躁／想發洩
- 每種心情對應專屬的氛圍描述與推薦曲目
- 點擊曲目直接跳轉 YouTube 收聽
- 提供 Spotify / YouTube 搜尋連結，方便探索更多
- 動態粒子背景，顏色隨心情切換

## 檔案結構

```
mood-player/
├── index.html   # 頁面結構 + JavaScript
└── style.css    # 樣式
```

## 使用方式

不需要安裝任何套件或建置工具，直接開啟即可。

```bash
# clone 專案
git clone https://github.com/your-username/mood-player.git

# 進入資料夾，用瀏覽器開啟
open index.html
```

或直接將 `index.html` 與 `style.css` 放在同一個資料夾，雙擊 `index.html` 開啟。

## 新增心情或曲目

編輯 `index.html` 內的 `moods` 物件：

```js
const moods = {
  // 新增一個心情 key
  yourMood: {
    color: '#HEXCOLOR',   // 主題色（十六進位）
    rgb: 'R,G,B',         // 同色的 RGB 值（供透明度使用）
    vibe: '氛圍描述文字',
    tracks: [
      {
        title: '歌曲名稱',
        artist: '歌手／樂團',
        note: '一句話描述',
        yt: 'YouTube 影片 ID'  // 無影片可省略此欄位
      },
    ],
    links: [
      {
        icon: '🎵',
        title: '搜尋更多',
        desc: '平台 — 關鍵字描述',
        url: '搜尋連結',
        platform: '平台名稱'
      },
    ]
  }
};
```

新增完後，在 HTML 加上對應按鈕：

```html
<button class="mood-btn" onclick="selectMood('yourMood', this)">按鈕文字</button>
```

## 技術

純原生 HTML / CSS / JavaScript，無任何外部依賴。
