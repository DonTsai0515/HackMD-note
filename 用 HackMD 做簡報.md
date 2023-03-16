# 用 HackMD 做簡報

參考源：[官方文件_簡報模式](https://hackmd.io/c/tutorials-tw/%2Fs%2Fhow-to-create-slide-deck-tw)

HackMD 整合了 [reveal.js](https://github.com/hakimel/reveal.js/)，讓我們可以用 Markdown 輕鬆寫簡報。讓我們開始吧！

:point_right: [點此看本份文件原始碼](https://hackmd.io/how-to-create-slide-deck-tw) :point_left: 


## 製作簡報與分頁

只要 HackMD 有支援的 Markdown 語法就能放進簡報裡面，無論是流程圖、內嵌 Youtube 影片或是 Latex 語法都行

我們用「三個連字號」（`-`）組成的「分隔線」來區別簡報的分頁，記得在前後各加上一個空行：

```markdown

# 簡報標題一

## 簡報標題二

---

- 清單
- 清單

```

### 產生的簡報

|||
|--|--|
|![](https://i.imgur.com/9D4vtZO.png)|![](https://i.imgur.com/2RT0N6b.png)|

:::info
:bulb: **提示：** 分隔線前後都要加空行，才能正確分頁！
:::

:::success
這裡有更詳細的範例：[Slide-example](/slide-example?both)
:::

### 你可以在編輯器裡預覽投影片！

只要在筆記最前面加入 [YAML 詮釋資料](https://hackmd.io/yaml-metadata-tw?both#type)，就可以直接在編輯器裡預覽簡報。

就像這樣：

```markdown
---
type: slide
---

<!-- 注意上面三行 -->

# 簡報標題一

## 簡報標題二

---

- 清單
- 清單

```

效果如下：

![](https://hackmd.io/_uploads/BJl2WsUsY.gif)


## 開啟筆記的簡報模式

![](https://i.imgur.com/lSsHlDZ.png)

1. 打開右上角的的共享選單「<i class="fa fa-share-alt fa-18"></i>」
2. 在在瀏覽模式的下拉選單裡，選擇「<i class="fa fa-tv"></i> **簡報模式**」
3. 按下「預覽」按鈕

便會在新分頁開啟筆記的簡報模式。

### 簡報總覽模式

![](https://i.imgur.com/iOoECtI.gif)

在簡報模式下，可以按下 <kbd>Esc</kbd> 鍵進入「總覽模式」，全部簡報一覽無遺 :eyes: 

在總覽模式下，我們用方向鍵切換不同的簡報頁面，按下 <kbd>Enter</kbd> 進入選擇的簡報頁面

### 講者模式

在簡報模式下按下 <kbd>s</kbd> 鍵，會彈出講者模式的獨立視窗。在這裡你可以看到這次簡報的用時，以及每張投影片的速記：

![](https://i.imgur.com/PsDFb4i.gif)

## 以章節組織簡報

在你的簡報中可能會有多個不同的主題，我們可以用「章節」的方式來組織這些頁面，無論是在總覽模式或是切換簡報時都會更有條理。

以 [HackMD - Markdown 協作筆記 @ 2016 MOPCON](/s/Ko4dxZc-TRmVxLhVL3ukHw) 這篇簡報為例，可以看到講者在「如何協作同步」、「資料儲存架構」、「如何記錄修訂版本」這幾個主題下（左右方向），分別加上了投影片去詳細描述不同主題（上下方向）。

![](https://i.imgur.com/xQ9Deac.png)

所以要如何建立簡報章節呢？您可以使用**四個連字號來分隔章節內簡報**：

```markdown
# 章節 1

---

# 章節 2

----

## 章節 2.1

----

## 章節 2.2

---

# 章節 3
```

#### 小結

一般的簡報用 `--- `（三個連字號）來分頁，章節內簡報用 `----`（四個連字號）來分頁，連字號前後都**必須有空行**來分隔頁面。

:::info
:bulb:**提示**：如果想要在一個章節之後接上一個普通的分頁，或是另開新章節，就是用三個連字號喔！
:::

## 下載簡報為 PDF 格式

在簡報模式頁面捲動到底部，會發現印表機的按鈕 <span class="fa fa-fw fa-print"></span>:

![](https://i.imgur.com/D8cLhmc.png)

點擊之後會進入簡報的**列印模式**，此時利用瀏覽器內建的「列印成 PDF」功能，就能把簡報輸出成 PDF 囉！

![](https://i.imgur.com/Gt3GW1v.png)


## 進階用法：自訂簡報樣式

### YAML 標頭設定

在筆記的最前面，我們可以加上 YAML 設定檔來自訂簡報選項：

舉例來說：

```yaml
---
title: 範例簡報        # 簡報的名稱
tags: presentation   # 簡報的標籤
slideOptions:        # 簡報相關的設定
  theme: solarized   # 顏色主題
  transition: 'fade' # 換頁動畫
  # parallaxBackgroundImage: 'https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg'
---
```

請確定 YAML 設定檔區塊的縮排是 **兩個空白**。在 YAML 格式中，我們在每行的最前面加上 `#`（井字符號）代表註解。註解內的設定值會被忽略。

更多的設定值請參考[可用的 YAML 設定值](#可用的-YAML-設定值)


---

## 進階用法：自訂單頁簡報樣式

使用 YAML 標頭的設定會影響整份簡報，如果只想要調整單頁的話，可以用這樣的語法來設定：

```
<!-- .slide: -->
```
例如，想要自訂簡報背景的話可以這麼做：

```markdown
---

<!-- .slide: data-background="https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg" -->

#### testslide

---
```

---

## 進階功能：簡報聚光燈

忘記帶簡報筆，或者線上會議只能用游標指示你說的重點？你可以使用簡報聚光燈！
在 YAML 設定檔加以下的設定值：

```yaml
---
slideOptions:
  spotlight:
    enabled: true
---
```

設定後開啟簡報模式，在畫面上按下左鍵，就會開啟聚光燈囉！

:::info
:bulb:**提示**：在聚光燈模式下，要用方向鍵 :arrow_left::arrow_up::arrow_down::arrow_right: 才能換頁哦！
:::

----

### Demo

![spotlight](https://i.imgur.com/dXhHcCP.gif)

---

## 進階功能：簡報倒數計時

想要在限定的時間內精準傳遞你的訊息，又不想一直看錶？可以用簡報倒數計時的功能來提示自己！
在 YAML 設定檔加上設定值：

```yaml
---
slideOptions:
  allottedMinutes: 5  # 預計一張簡報花幾分鐘
---
```

設定後開啟簡報模式，會看到原本藍色簡報進度條的上方多了紅色的長條，代表目前經過的時間，與進度條對照就會清楚目前簡報的用時，是超前還是落後 :running: 

----

### Demo

![Timer](https://i.imgur.com/l5Akz4B.gif)

---

## 可用的 YAML 設定值

```yaml
# Display controls in the bottom right corner
controls: true

# Display a presentation progress bar
progress: true

# Set default timing of 2 minutes per slide
defaultTiming: 120

# Display the page number of the current slide
slideNumber: false

# Push each slide change to the browser history
history: false

# Enable keyboard shortcuts for navigation
keyboard: true

# Enable the slide overview mode
overview: true

# Vertical centering of slides
center: true

# Enables touch navigation on devices with touch input
touch: true

# Loop the presentation
loop: false

# Change the presentation direction to be RTL
rtl: false

# Randomizes the order of slides each time the presentation loads
shuffle: false

# Turns fragments on and off globally
fragments: true

# Flags if the presentation is running in an embedded mode,
# i.e. contained within a limited portion of the screen
embedded: false

# Flags if we should show a help overlay when the questionmark
# key is pressed
help: true

# Flags if speaker notes should be visible to all viewers
showNotes: false

# Global override for autolaying embedded media (video/audio/iframe)
# - null: Media will only autoplay if data-autoplay is present
# - true: All media will autoplay, regardless of individual setting
# - false: No media will autoplay, regardless of individual setting
autoPlayMedia: null

# Number of milliseconds between automatically proceeding to the
# next slide, disabled when set to 0, this value can be overwritten
# by using a data-autoslide attribute on your slides
autoSlide: 0

# Stop auto-sliding after user input
autoSlideStoppable: true

# Use this method for navigation when auto-sliding
autoSlideMethod: Reveal.navigateNext

# Enable slide navigation via mouse wheel
mouseWheel: false

# Hides the address bar on mobile devices
hideAddressBar: true

# Opens links in an iframe preview overlay
previewLinks: false

# Transition style
transition: 'slide' 
# none/fade/slide/convex/concave/zoom

# Transition speed
transitionSpeed: 'default'
# default/fast/slow

# Transition style for full page slide backgrounds
backgroundTransition: 'fade'
# none/fade/slide/convex/concave/zoom

# Number of slides away from the current that are visible
viewDistance: 3

# Parallax background image
parallaxBackgroundImage: ''
# e.g. "'https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg'"

# Parallax background size
parallaxBackgroundSize: ''
# CSS syntax, e.g. "2100px 900px"

# Number of pixels to move the parallax background per slide
# - Calculated automatically unless specified
# - Set to 0 to disable movement along an axis
parallaxBackgroundHorizontal: null
parallaxBackgroundVertical: null

# The display mode that will be used to show slides
display: 'block'

# Enable spotlight mode
spotlight:
  enabled: true
  
# Enable timer (in minutes)
allottedMinutes: 5
```