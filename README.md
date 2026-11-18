# ai-course-sfx：短影音音效＋背景音樂庫（給 AI 剪片用）

這是 94 AI 實戰班的公開素材庫。學員用手機叫 Claude 剪片時，只要給它這個網址，Claude 就能自己讀索引、自己挑音效和音樂、自己下載來用。

- 音效 19 個（`sfx/`）：柔和、有質感，沒有唰聲、沒有金屬叮、沒有電子尖音
- 背景音樂 8 首（`bgm/`）：每首 40～50 秒，開頭淡入、結尾 3 秒自然淡出
- 天麗產品去背圖 22 張（`products/`）：透明底 PNG

## 給 AI 的使用方法（請照順序）

1. **先讀索引**：
   ```
   curl -L https://raw.githubusercontent.com/nico31319/ai-course-sfx/main/index.json
   ```
   每一筆有 `type`（sfx／bgm／product）、`category`（用途分類）、`mood`（聽起來的感覺）、`use_when`（什麼畫面適合用）、`duration_sec`、`loudness`、`raw_url`。
2. **依畫面挑檔**：看 `use_when` 找最貼近的；同一支影片音效種類不要太多（3～5 種就夠），背景音樂整支只用 1 首。
3. **下載**：`curl -L -o 檔名 <raw_url>`
4. **混音規則**：
   - 人聲最大。音效比人聲小約 6～10 dB，對準畫面出現的那一格。
   - 背景音樂比人聲小約 20 dB（有人講話時再壓低，沒人講話的空檔可稍微拉回來）。
   - 音樂頭尾加淡入淡出（淡入 0.5 秒、淡出 1～2 秒）；影片比音樂長就重複接一次，接縫處交叉淡化 1 秒。
5. **素材規格**：音效峰值統一約 −14 dBFS、頭尾已去靜音並加 5～10ms 淡入淡出；音樂整合響度統一約 −20 LUFS；全部 mp3、44.1 kHz。

### 用途分類一覽

| 分類 | 檔名開頭 | 用在 |
|---|---|---|
| 進場 | `pop_` | 字卡、圖示、貼紙彈出 |
| 重點出現 | `notice_` | 重點句、關鍵字框 |
| 步驟／數字 | `tap_`、`tick_` | 清單逐條、步驟 1-2-3、數字跳動 |
| 轉場 | `transition_` | 換段落（很輕，不是唰聲） |
| 完成 | `done_` | 完成、打勾、成果揭曉 |
| 生活感 | `page_flip_`、`book_place_`、`water_drop_`、`typing_keys_`、`shutter_click_` | 翻頁、放書、水滴、打字、拍照 |

## 音效清單與出處

| 檔名 | 分類 | 感覺 | 長度 | 原始檔 | 出處 | 授權 |
|---|---|---|---|---|---|---|
| `pop_soft_01.mp3` | 進場 | 輕柔、圓潤的小 pop | 0.19 秒 | Kenney – Interface Sounds（drop_002.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `pop_soft_02.mp3` | 進場 | 短促、俏皮的撥弦 pop | 0.11 秒 | Kenney – Interface Sounds（pluck_002.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `pop_bubble_03.mp3` | 進場 | 軟軟的泡泡 pop，尾音稍長 | 0.28 秒 | Kenney – Interface Sounds（drop_004.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `notice_soft_01.mp3` | 重點出現 | 柔和、上揚的提示音 | 0.48 秒 | Kenney – Interface Sounds（question_001.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `notice_low_02.mp3` | 重點出現 | 低沉溫和的提示音 | 0.32 秒 | Kenney – Interface Sounds（question_004.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `tap_soft_01.mp3` | 步驟數字 | 輕輕的點擊 | 0.09 秒 | Kenney – UI Audio（click1.ogg） | [kenney.nl](https://kenney.nl/assets/ui-audio) | CC0 1.0 |
| `tap_soft_02.mp3` | 步驟數字 | 很短很輕的點 | 0.05 秒 | Kenney – UI Audio（click2.ogg） | [kenney.nl](https://kenney.nl/assets/ui-audio) | CC0 1.0 |
| `tap_wood_03.mp3` | 步驟數字 | 溫潤的木頭輕敲 | 0.1 秒 | Kenney – Impact Sounds（impactWood_light_000.ogg） | [kenney.nl](https://kenney.nl/assets/impact-sounds) | CC0 1.0 |
| `tick_soft_04.mp3` | 步驟數字 | 細小清脆的 tick | 0.06 秒 | Kenney – Interface Sounds（tick_004.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `transition_cloth_01.mp3` | 轉場 | 布料輕擦，非常輕 | 0.28 秒 | Kenney – RPG Audio（cloth2.ogg） | [kenney.nl](https://kenney.nl/assets/rpg-audio) | CC0 1.0 |
| `transition_card_02.mp3` | 轉場 | 紙卡輕滑 | 0.58 秒 | Kenney – Casino Audio（card-slide-2.ogg） | [kenney.nl](https://kenney.nl/assets/casino-audio) | CC0 1.0 |
| `transition_card_03.mp3` | 轉場 | 一疊紙卡輕輕展開 | 0.72 秒 | Kenney – Casino Audio（card-fan-1.ogg） | [kenney.nl](https://kenney.nl/assets/casino-audio) | CC0 1.0 |
| `done_chime_01.mp3` | 完成 | 柔和低音叮咚 | 0.28 秒 | Kenney – Interface Sounds（confirmation_001.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `done_chime_02.mp3` | 完成 | 明亮但柔和的兩音提示 | 0.48 秒 | Kenney – Interface Sounds（confirmation_004.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `page_flip_01.mp3` | 生活感 | 翻一頁紙（已降高頻） | 0.36 秒 | Kenney – RPG Audio（bookFlip2.ogg） | [kenney.nl](https://kenney.nl/assets/rpg-audio) | CC0 1.0 |
| `book_place_01.mp3` | 生活感 | 書本輕放在桌上 | 0.23 秒 | Kenney – RPG Audio（bookPlace2.ogg） | [kenney.nl](https://kenney.nl/assets/rpg-audio) | CC0 1.0 |
| `water_drop_01.mp3` | 生活感 | 圓潤的水滴聲 | 0.19 秒 | Kenney – Interface Sounds（drop_003.ogg） | [kenney.nl](https://kenney.nl/assets/interface-sounds) | CC0 1.0 |
| `typing_keys_01.mp3` | 生活感 | 幾下輕輕打字聲（約 0.7 秒） | 0.72 秒 | Kenney – UI Audio（click1+click2+click5 合成 6 下） | [kenney.nl](https://kenney.nl/assets/ui-audio) | CC0 1.0 |
| `shutter_click_01.mp3` | 生活感 | 兩段機械喀擦，類似相機快門 | 0.3 秒 | Kenney – UI Audio（switch11+switch30 合成） | [kenney.nl](https://kenney.nl/assets/ui-audio) | CC0 1.0 |

音效全部來自 Kenney（https://kenney.nl），各音效包內附 `License.txt` 寫明 Creative Commons Zero（CC0 1.0）。
處理方式：頭尾去靜音、低通濾波去掉刺耳高頻、加淡入淡出、峰值統一到 −14 dBFS；`typing_keys_01`、`shutter_click_01` 是用 Kenney 的點擊聲／開關聲合成的。
挑選時用頻譜數據把高頻能量太高（8 kHz 以上能量 > 5%）的音效排除。

## 背景音樂清單與出處

| 檔名 | 類型 | 感覺 | 長度 | 原曲 | 出處 | 授權 |
|---|---|---|---|---|---|---|
| `bgm_piano_gentle.mp3` | 溫柔鋼琴 | 溫柔、抒情的鋼琴旋律 | 45.0 秒 | FreePD – 〈Lovely Piano Song〉by Rafael Krux，從第 0 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2021/https://freepd.com/romantic.php) | CC0 1.0 |
| `bgm_ukulele_happy.mp3` | 輕快烏克麗麗 | 開心、正向的烏克麗麗＋輕打擊 | 40.0 秒 | FreePD – 〈Ukulele Song〉by Rafael Krux，從第 0 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2024/https://freepd.com/upbeat.php) | CC0 1.0 |
| `bgm_lofi_relax.mp3` | lo-fi 輕鬆 | 像舊唱片的 lo-fi 放鬆感 | 50.0 秒 | FreePD – 〈Study and Relax〉by Kevin MacLeod，從第 0 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2021/https://freepd.com/misc.php) | CC0 1.0 |
| `bgm_strings_elegant.mp3` | 優雅弦樂 | 古典弦樂五重奏小步舞曲，優雅 | 45.0 秒 | FreePD – 〈The Celebrated Minuet〉by Rafael Krux（改編 Boccherini 弦樂五重奏），從第 0 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2021/https://freepd.com/misc.php) | CC0 1.0 |
| `bgm_pop_bright.mp3` | 活潑流行 | 明亮有活力、略帶切分的流行節奏 | 40.0 秒 | FreePD – 〈City Sunshine〉by Kevin MacLeod，從第 0 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2024/https://freepd.com/upbeat.php) | CC0 1.0 |
| `bgm_chill_neutral.mp3` | 時尚 chill | 中性、舒服、不搶戲的 chill | 45.0 秒 | FreePD – 〈Natural Vibes〉by Kevin MacLeod，從第 0 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2024/https://freepd.com/upbeat.php) | CC0 1.0 |
| `bgm_guitar_warm.mp3` | 溫暖吉他 | 撥弦吉他，鄉村感、溫暖踏實 | 40.0 秒 | FreePD – 〈Still Pickin〉by Kevin MacLeod，從第 0 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2024/https://freepd.com/upbeat.php) | CC0 1.0 |
| `bgm_kalimba_calm.mp3` | 療癒放鬆 | 拇指琴（卡林巴）輕柔放鬆 | 50.0 秒 | FreePD – 〈Kalimba Relaxation Music〉by Kevin MacLeod，從第 2.3 秒起剪，結尾 3 秒自然淡出 | [存檔頁](https://web.archive.org/web/2021/https://freepd.com/misc.php) | CC0 1.0 |

音樂全部來自 FreePD（freepd.com，Kevin MacLeod 主持的公眾領域音樂站）。FreePD 首頁寫明「This music is all licensed CC0 1.0 Universal Public Domain Dedication」（存檔：https://web.archive.org/web/2024/https://freepd.com/ ）。
FreePD 已在 2025 年關站，原檔是從 Internet Archive Wayback Machine 保存的 freepd.com 原始網址下載；表格裡的「存檔頁」是當年該曲所在的分類頁，可看到曲名、作者。
處理方式：從原曲開頭剪 40～50 秒、淡入 0.3 秒、結尾 3 秒淡出、響度統一到 −20 LUFS。

## 天麗產品去背圖：給天麗夥伴做產品動畫用

`products/` 是天麗生技的產品去背圖（透明底 PNG，高度 1400 px 以內、每張 1 MB 以下），給天麗夥伴做產品動畫、MG 動畫、產品介紹畫面時直接抓。
保養品 14 支來自天麗官方去背圖；保健品 8 支來自天麗官網產品頁（https://tenlead.com/product-category/health/ ），保留官網圖原本的淡淡倒影。

| 檔名 | 品名 | 尺寸 | 分類 |
|---|---|---|---|
| `tl_01_cleansing_lotion.png` | 1號 雙效潔顏露 | 326×1400 | 天麗保養品 |
| `tl_02_balancing_toner.png` | 2號 平衡柔膚露 | 325×1400 | 天麗保養品 |
| `tl_03_firming_eye_cream.png` | 3號 全效緊緻眼霜 | 290×1400 | 天麗保養品 |
| `tl_04_brightening_cream.png` | 4號 煥白晶華霜 | 368×1396 | 天麗保養品 |
| `tl_05_balancing_cream.png` | 5號 均衡調理霜 | 368×1386 | 天麗保養品 |
| `tl_06a_brightening_protective_cream.png` | 6A 亮白防護霜（保濕） | 277×1340 | 天麗保養品 |
| `tl_06b_tinted_protective_cream.png` | 6B 潤白防護霜（潤色） | 275×1337 | 天麗保養品 |
| `tl_08_revitalizing_essence_cream.png` | 8號 賦活精華霜 | 359×1359 | 天麗保養品 |
| `tl_09_repairing_cream.png` | 9號 保濕修護霜 | 362×1307 | 天麗保養品 |
| `tl_10_vitamin_c_serum.png` | 10號 瞬效亮麗精純C液 | 225×1400 | 天麗保養品 |
| `tl_12_youth_essence.png` | 12號 煥采青春露 | 266×1333 | 天麗保養品 |
| `tl_ai_deep_cleansing_oil.png` | AI 深層潔膚油 | 323×1400 | 天麗保養品 |
| `tl_bio_snow_mask.png` | Bio 雪肌面膜 | 782×1269 | 天麗保養品 |
| `tl_whitening_c_powder.png` | 嫩白C粉 | 231×1252 | 天麗保養品 |
| `tl_supp_youth_element_f.png` | 青春元素-F | 961×740 | 天麗保健品 |
| `tl_supp_radiance_element_l.png` | 亮采元素-L | 978×741 | 天麗保健品 |
| `tl_supp_slim365_gen2.png` | 纖麗 365（二代） | 981×756 | 天麗保健品 |
| `tl_supp_slim365_s1.png` | 纖麗 365 酵素 S1 | 1015×745 | 天麗保健品 |
| `tl_supp_olive_oil.png` | 麗瑞頂級橄欖油 | 933×512 | 天麗保健品 |
| `tl_supp_redginseng.png` | 天麗紅蔘精華飲 | 409×398 | 天麗保健品 |
| `tl_supp_deluxe_plus.png` | 麗穩康 | 327×524 | 天麗保健品 |
| `tl_supp_royal_plus.png` | 麗穩膳 | 327×519 | 天麗保健品 |

> ⚠️ 產品圖**不是** CC0，著作權屬天麗生技，只供天麗夥伴宣傳天麗產品使用。

## 授權

見 [LICENSE](LICENSE)。簡單說：`sfx/`、`bgm/` 的素材原作者以 CC0／公眾領域釋出，這裡的整理、剪輯、索引也以 CC0 釋出，可商用、不用標示出處（標了更好：音效 Kenney、音樂 FreePD 各曲作者）。`products/` 除外。
