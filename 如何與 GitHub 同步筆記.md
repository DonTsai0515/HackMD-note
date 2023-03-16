# 如何與 GitHub 同步筆記

可以將筆記與 GitHub 上的 Markdown 文件同步，確保在各個平台上都保持同步。

## 建立筆記連結

在同步筆記之前，需要先建立筆記和 GitHub 檔案的連結。
1. 在空白筆記的編輯器找到連結的選項。
2. 在 <i class="fa fa-history"></i> **版本** 選單裡面進行操作。

## 授權 HackMD 存取 GitHub

如果是第一次同步 HackMD 筆記到 GitHub，GitHub 會要求**授權 HackMD GitHub App 存取帳號** 和 **安裝 app 在 repo (專案)上**

### 1. 授權個人帳號

HackMD GitHub App 需要授權才能知道所有有權讀取的 repo 有哪些：包含個人的 repo 及所屬組織擁有的 repo

### 2. 授權 Repo（安裝 App 到 Repo）

在授權個人帳號之後，GitHub 就會讓您選擇要在哪些 repo 上安裝 HackMD GitHub App
可以稍後再回來授權更多 repo

:::info
:bulb: **小提示：** 也可以直接[到 GitHub 上安裝](https://github.com/apps/hackmd-hub) HackMD 的 GitHub App。
:::

## 初次連結筆記

在第一次推送 (push) HackMD 筆記或是拉取 (pull) GitHub 檔案的時候，可以選擇要連結這篇筆記到哪個 repo、哪個 branch、哪份 Markdown 檔案。
也可以在連結的時候手動新增 branch 或是新增檔案。

:::warning
:warning: **注意：** HackMD 會切換您的換行規則，以和 GitHub 的換行規則保持一致。

![](https://i.imgur.com/qHjm5D3.png)
:::

## 和 GitHub 保持同步

在筆記建立連結以後，連結的 repo 和檔案路徑就會出現在 <i class="fa fa-history"></i> **版本** 選單上方。
可以從這裡 push 之前儲存過的筆記版本到 Github 上，或是 pull GitHub 上的更動。

![](https://i.imgur.com/BrwJXxQ.png)

### 嵌入 GitHub badge

在筆記建立連結以後，可以點擊 <i class="fa fa-history"></i> **版本** 選單上方的 <i class="fa fa-link"></i> **嵌入 Badge** 按鈕在筆記的上方嵌入 GitHub badge。
透過這個 badge，在 GitHub 上的社群就可以輕鬆地加入討論或是貢獻文件。

![](https://i.imgur.com/Lypku77.png)

### 推送 (Push) 版本到 GitHub

可以選擇要 push 哪些命名版本到 GitHub 上，每個命名版本都會被視為一個 commit，版本的名稱和描述則會被存為該 commit 的 commit message。

### 從 GitHub 拉取 (Pull) 版本

可以從 GitHub 不同的 branch 上 pull 最新的版本下來， 並選擇要將套用哪些變更。
:::info
:bulb: **小提示：** HackMD 會在 pull 之前先自動存檔一個名為 `before pull from <branch>` 的版本。
由於 HackMD 不會在 pull 的時候將筆記鎖住，可能仍會有人進行變更。如果想要復原，需要回到編輯器後用 `ctrl + z` (或`cmd + z`) 來復原匯入。
:::

---
## 授權更多 Repo

如果在連結筆記的時候找不到想要連結的 repo，您可以授權更多 repo。

![](https://i.imgur.com/dLoJvyy.png)

## 取消授權及解除安裝

如前所述，授權分成兩層：帳號及 repo

1. 如果要取消帳號的授權，可以在這裡找到選項：
[https://github.com/settings/apps/authorizations](https://github.com/settings/apps/authorizations)
2. 如果要解除個人 repo 上安裝的 HackMD GitHub App，可以在這裡找到選項：
[https://github.com/settings/installations](https://github.com/settings/installations)
3. 如果要解除安裝在所屬的 GitHub Organization 上 repo 的 app，可以在這裡找到選項：
[https://github.com/organizations/your\_organization\_name/settings/installations](https://github.com/organizations/your_organization_name/settings/installations)

---
---
## 換行顯示規則

HackMD 遵循 [CommonMark 標準](https://spec.commonmark.org/0.29/) (**標準**) 所規定的Markdown 語法，所以筆記才可以和其他平台的 Markdown 相容。

換行大致分為兩種：

1. #### 硬換行

在編輯器裡面敲入 Enter (或是 Return) 的時候，實際上是輸入了一個 “換行符號”。敲入這個符號通常是想要從新的一行開始繼續輸入，所以 HackMD 就直接幫您換一個新行（將 “換行符號” 顯示為 HTML 的 `<br />`）。這種作法在 **標準** 裡被稱為 [**硬換行**](https://spec.commonmark.org/0.29/#hard-line-breaks)。

2. #### 軟換行

“換行符號” 還有另外一種處理方式（在 **標準** 裡稱為[軟換行](https://spec.commonmark.org/0.29/#soft-line-breaks)）。敲入的 “換行符號” 在編輯器裡面會看到文字確實換了新行，但是在 HTML 的顯示上，則只顯示了一個空白鍵 。這是 <font color=red>GitHub</font> 對 “換行符號” 的處理方法。

---
在軟換行的處理方式下，想要在 HTML 裡面顯示換新行（將 “換行符號” 顯示為 HTML 的 `<br />`）的時候，可以用以下兩種方式來表示：

1. 在換行符號前輸入兩個空白鍵：

```
第一行 Space Space Enter  
第二行
```

2. 在換行符號前輸入一個反斜線：

```
第一行 \ Enter
第二行
```

* 因為 HackMD 和 GitHub 對換行規則的處理方式不同，如果沒有切換筆記的換行規則、又將該篇筆記和 GitHub 同步的話，筆記在 GitHub 上會和在 HackMD 上看起來不太一樣。  

### 如何切換換行規則呢？  

1. 可以在 <i class="fa fa-gear"></i> [**設定**](https://hackmd.io/settings) 調整所有 “未來新增的筆記” 的換行規則。  
2. 可以在編輯器下方的 **換行** 按鈕裡切換換行規則。  
3. 可以用 YAML 來個別設定每篇筆記的換行規則。  
    * 將以下這三行放在筆記的最前面。  
```
---
breaks: false  # false 表示採用 "軟換行規則"，即 "換行符號" 不會換到新行。
---
```    