# 前端待辦清單

**前端待辦清單** 是一份詳細的清單，用來檢查你的網站或網頁發布到正式環境前所有需要測試的項目。

**其他待辦清單：**

- [🎮 Front-End Performance Checklist](https://github.com/thedaviddias/Front-End-Performance-Checklist#---------front-end-performance-checklist-)
- [💎 Front-End Design Checklist](https://github.com/thedaviddias/Front-End-Design-Checklist#front-end-design-checklist)

> [!TIP]
> ⭐️ 那些開發者絕對不能錯過的 UX 設計技巧 👉 [UX Patterns for Devs](https://uxpatterns.dev/en) ⭐️

## 📚目錄

- [使用方式](#使用方式)
- [Head](#head)
- [HTML](#html)
- [Webfonts 網頁字體](#webfonts-網頁字體)
- [CSS](#css)
- [Images](#images)
- [JavaScript](#javascript)
- [Security 安全性](#security-安全性)
- [Performance 效能](#performance-效能)
- [Accessibility 無障礙](#accessibility-無障礙)
- [SEO](#seo)
- [Translations](#translations)
- [Support](#support)
- [Contributors](#contributors)
- [Backers](#backers)
- [Sponsors](#sponsors)
- [License](#license)

## 使用方式
<!-- prettier-ignore-start -->
> [!IMPORTANT]
> **提醒一下：** 這份檢查清單是根據前端開發者多年的經驗整理出來的，還參考了許多開源清單的內容！
<!-- prettier-ignore-end -->


**前端待辦清單**中的所有項目皆來是大多數專案的需求，針對你的專案時，還是會有某些項目用不到、可以忽略（例如，在行政用途的網頁 APP 中，你可能不需要 RSS 的訂閱功能）。我們依照可以調動的靈活性區分為三個等級：

* ![Low][low_img] 代表這是個**推薦**項目，但在特定的情況下可以忽略。
* ![Medium][medium_img] 代表這是**高度推薦**項目，在非常少數的特定情況下可以忽略。其中某些項目，如果忽略了會使效能或 SEO 結果（指搜尋引擎上的排名）很糟。
* ![High][high_img] 代表這是任何情況下都**不能忽略**的項目。忽略可能在你的網頁、網頁親和力或 SEO 上造成功能失常。這些項目的測試優先度最高。

某些資源有標示符號，協助你瞭解在清單中找到的內容或協助的類型：

* 📖: 文檔或文章
* 🛠: 網路工具 / 測試工具
* 📹: 媒體或影片內容

## Head

<!-- prettier-ignore-start -->
> [!NOTE]
> **補充：** 這有[一份列表](https://github.com/joshbuchea/HEAD)可以找到所有 HTML `<head>`裡面可能含有的東西。
<!-- prettier-ignore-end -->

### Meta 標籤

- [ ] **Doctype （檔案類型）:** ![High][high_img] Doctype 是 HTML5，需要放在 HTML 檔案內的最上面。

<!-- prettier-ignore-start -->
```html
<!doctype html><!-- HTML5 -->
```
<!-- prettier-ignore-end -->

- 📖
  [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

_而接下來 Charset 和 Viewport 這兩個 `<meta>` 標籤一定要放在 `<head>` 內的最前面！_

- [ ] **Charset（字符）:** ![High][high_img] 正確宣告字符編碼（UTF-8）。

<!-- prettier-ignore-start -->
```html
<!-- Set character encoding for the document -->
<meta charset="utf-8">
```
<!-- prettier-ignore-end -->

- [ ] **Viewport（視點）:** ![High][high_img] 正確宣告 viewport 設定。

<!-- prettier-ignore-start -->
```html
<!-- Viewport for responsive web design -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```
<!-- prettier-ignore-end -->

- [ ] **Title（標題）:** ![High][high_img] 所有頁面都有使用一個標題 （SEO: Google 會計算 title 上使用的字符寬度，只會偵測到 472px ~ 482px 之間。平均最大值是 55 個字符）

```html
<!-- Document Title -->
<title>Page Title less than 55 characters</title>
```

- 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
- 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

- [ ] **Description（描述）:** ![High][high_img] 有設置 meta description，每個頁面只有一個且長度不能超過150字元。

<!-- prettier-ignore-start -->
```html
<!-- Meta Description -->
<meta name="description" content="Description of the page less than 150 characters">
```
<!-- prettier-ignore-end -->

- 📖
  [Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

- [ ] **Favicons（網站圖示）:** ![Medium][medium_img] 每一個 favicon 都需要創立且被正確展示。如果你只有一個 `favicon.ico`，可以將它置於網站的根目錄好讀取。通常你不需要對它設定。然而現在還是建議照下方的範例手動連結，以確保最佳實踐。現在比起 `.icon` 比較推薦 PNG 檔案格式。（大小最少需要: 32x32px）

<!-- prettier-ignore-start -->
```html
<!-- Standard favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Recommended favicon format -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
<!-- Recommended modern favicon format (not recommended for legacy browsers) -->
<link rel="icon" type="image/svg+xml" href="https://example.com/favicon.svg">
```
<!-- prettier-ignore-end -->

- 🛠 [Favicon Generator](https://www.favicon-generator.org/)
- 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
- 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
- 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
- 📖 [PNG favicons - caniuse](https://caniuse.com/link-icon-png)

- [ ] **Apple Web App Meta:** ![Low][low_img] 包含 Apple 專用的 Meta 標籤。

<!-- prettier-ignore-start -->
```html
<!-- Apple Touch Icon (at least 200x200px) -->
<link rel="apple-touch-icon" href="/custom-icon.png">

<!-- To run the web application in full-screen -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- Status Bar Style (see Supported Meta Tags below for available values) -->
<!-- Has no effect unless you have the previous meta tag -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">
```
<!-- prettier-ignore-end -->

- 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)
- 📖 [Supported Meta Tags](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

- [ ] **Windows Tiles:** ![Low][low_img] 設置並連結 Windows Titels

<!-- prettier-ignore-start -->
```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml">
```
<!-- prettier-ignore-end -->

`browserconfig.xml` 檔案中 xml 的最小設定值如下:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

<!-- prettier-ignore-start -->
- 📖 [Browser configuration schema reference](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/dn320426(v=vs.85))
<!-- prettier-ignore-end -->

- [ ] **Canonical（原典）:** ![Medium][medium_img] 使用 `rel="canonical"` 避免重複的內容。

<!-- prettier-ignore-start -->
```html
<!-- Helps prevent duplicate content issues -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-read.html">
```
<!-- prettier-ignore-end -->

- 📖
  [Use canonical URLs - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
- 📖
  [5 common mistakes with rel=canonical - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML 標籤

- [ ] **Language attribute（語言標籤）** ![High][high_img] 語言屬性 `lang` 在網頁中被指定且與當前頁面的語言是相關的。

```html
<html lang="en"></html>
```

- [ ] **Direction attribute（方向標籤）:** ![Medium][medium_img] 文字閱讀方向有被設定在 body 標籤內（也可以用在其他 HTML 標籤裡）。

```html
<html dir="rtl">
  <!-- ... -->
</html>
```

- 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

> 註: dir 中的 rtl 是 right to left 縮寫，而 ltr 則是 left to right 的縮寫

- [ ] **Alternate language（備用語言）:** ![Low][low_img] 語言標籤在網頁中被指定且與當前頁面的語言是相關的。

<!-- prettier-ignore-start -->
```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```
<!-- prettier-ignore-end -->

- [ ] **x-default:** ![Low][low_img] 你的網站用於國際著陸頁（Landing Pages）的語言標籤。

```html
<link rel="alternate" href="https://example.com/" hreflang="x-default" />
```

- 📖 [x-default - Google](https://webmasters.googleblog.com/2013/04/x-default-hreflang-for-international-pages.html)

- [ ] **Conditional comments（條件備註）:** ![Low][low_img] 如果有需要，已經為 IE 設定 Conditional comments。

- 📖
  [About conditional comments (Internet Explorer) - MSDN - Microsoft](<https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx>)

- [ ] **RSS feed（RSS 訂閱）:** ![Low][low_img] 如果網站是部落格或者會分享文章，設置 RSS 連結。

- [ ] **CSS Critical（最小 CSS 合集）:** ![Medium][medium_img] CSS critical 將使用在頁面顯示部分的核心 CSS 收集起來，在主要的CSS被呼叫之前就先渲染。它以放置於<style></style>間的形式嵌在檔案中(單行形式、最小化)。

- 🛠 [Critical by Addy Osmani on GitHub](https://github.com/addyosmani/critical) 使這一過程自動化。

- [ ] **CSS order（CSS 順序）:** ![High][high_img] 在 `<head>` 哩，所有 CSS 檔案都要在 JS 檔案前被載入。（例外狀況: 當 JS 檔案以非同步方式在頁面上方被載入）

### 社交媒體的 meta 標籤

使用以下方式視覺化並自動產生我們的社交標籤 [Meta Tags](https://metatags.io/)

針對所有網頁都高度推薦 **_Facebook OG_** 與 **_Twitter Cards_**。關於其他社交媒體的標籤，當你有特別想要確保的社交媒體的顯示功能再考慮。

- [ ] **Facebook Open Graph（FB 開放圖形）:** ![Low][low_img] 所有 Facebook Open Graph (OG) 都有測試過且沒有遺漏掉或出現失敗的訊息。圖檔最小需要 600x315px，推薦大小 1200x630px。

<!-- prettier-ignore-start -->
> [!NOTE]
> 利用 `og:image:width` 與 `og:image:height` ，其會向社交網站的爬蟲指定圖片尺寸，以便它可以立即呈現圖片，不需要再非同步載入並處理它。
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here" />
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<!-- Next tags are optional but recommended -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```
<!-- prettier-ignore-end -->

- 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
- 📖 [Best practices - Sharing](https://developers.facebook.com/docs/sharing/best-practices/)
- 🛠 利用 [Facebook OG testing](https://developers.facebook.com/tools/debug/) 測試你的網頁

- [ ] **Twitter Card:** ![Low][low_img]

<!-- prettier-ignore-start -->
```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```
<!-- prettier-ignore-end -->

- 📖
  [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
- 🛠 利用 [Twitter card validator](https://cards-dev.twitter.com/validator) 測試你的網頁

**[⬆ 返回目錄](#目錄)**

## HTML

### 最佳實踐

- [ ] **HTML5 Semantic Elements（HTML5 語意元素）:** ![High][high_img] HTML5 Semantic Elements 語意元素被適當使用(header, section, footer, main...)。

- 📖 [HTML Reference](http://htmlreference.io/)

- [ ] **Error pages（錯誤頁面）:** ![High][high_img] 404 錯誤頁面跟存在 5xx 錯誤的情況需要它自己的 CSS 程式碼(不要從當前的服務向外呼叫)。

- [ ] **Noopener:** ![Medium][medium_img] 注意當你有外部連結且使用 `target="_blank"` 時，在連結加上 `rel="noopener"`，可以避免 tab nabbing (開啟新 tab 時造成原頁面效能低落)。若你要支援舊版 Firefox，使用 `rel="noopener noreferrer"`。
- 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

- [ ] **Clean up comments（清除註解）:** ![Low][low_img] 頁面發表前將沒有效果的程式碼清除。

### HTML 測試

- [ ] **W3C compliant（W3C 兼容）:** ![High][high_img] 所有頁面都要經過 W3C 檢測器的測試，確保沒有 HTML 程式碼的問題。

- 🛠 [W3C validator](https://validator.w3.org/)

- [ ] **HTML Lint:** ![High][high_img] 我使用工具分析自己的 HTML 程式碼，幫助我發現任何可能的問題。

- 🛠 [Dirty markup](https://www.10bestdesign.com/dirtymarkup/)

- 🛠 [webhint](https://webhint.io/)

- [ ] **Link checker（連結確認器）:** ![High][high_img] 使用 Link checker 確保沒有任何無效連結，避免出現任何 404 error。

- 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

- [ ] **Adblockers test（廣告阻擋外掛測試）:** ![Medium][medium_img] 測試你的頁面在廣告阻斷程式運作的情況下能正確顯示（你可以顯示訊息慫恿使用者關閉廣告阻斷程式）。

- 📖
  [Use AdBlocking in your Dev Environment](https://andreicioara.com/use-adblocking-in-your-dev-environment-48db500d9b86)

**[⬆ 返回目錄](#目錄)**

---

## Webfonts 網頁字體

> [!NOTE]
> 使用 Web 字體（Webfonts）可能會導致 FOUT（文字閃爍異常） 或 FOIT（文字不可見異常）。
> 請考慮使用後備字體或利用 webfont 網頁字體加載器來控制行為。

- 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

- [ ] **Webfont format（網頁字體格式）:** ![High][high_img]  所有瀏覽器都支援 WOFF、WOFF2 跟 TTF 字體。

- 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/woff).
- 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/woff2).
- 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/ttf)
- 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

- [ ] **Webfont size（網頁字體大小）:** ![High][high_img] 網頁字體檔案大小不能超過 2MB （包含所有字體）。

- [ ] **Webfont loader（網頁字體加載器）:** ![Low][low_img] 利用 webfont loader 網頁字體加載器控制載入的行為。

- 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ 返回目錄](#目錄)**

---

## CSS

> **補充：** 參考這些 CSS 標準與指南，以維持最佳實踐！
> [CSS guidelines](https://cssguidelin.es/) 和 [Sass Guidelines](https://sass-guidelin.es/) 是大多數前端開發者遵循的標準。
> 如果你對 CSS 屬性有疑問，可查閱 [CSS Reference](http://cssreference.io/)。
> 此外還有一份簡潔的 [Code Guide](http://codeguide.co/) ，可用來維持程式碼的一致性！

- [ ] **Responsive Web Design（網站響應式設計）:** ![High][high_img] 網站有使用響應式設計。
- [ ] **CSS Print（CSS 列印）:** ![Medium][medium_img] 每個頁面都正確設置列印樣式。
- [ ] **Preprocessors（預處理器）:** ![Low][low_img]  你的頁面有使用 CSS 預處理器（推薦 [Sass](http://sass-lang.com/),
      [Less](http://lesscss.org/), [Stylus](http://stylus-lang.com/)）.
- [ ] **Unique ID（唯一 ID）:** ![High][high_img] 使用 ID 的時候確保個別頁面裡沒有重複 ID。
- [ ] **Reset CSS（重置 CSS 樣式）:** ![High][high_img] 確保 CSS reset （reset, normalize or reboot）被使用 _(如果你使用 CSS 框架，例如 Bootstrap 或 Foundation，Normalize 已經包含在裡面)_。

- 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
- 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
- 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

- [ ] **JS prefix（區分 JS 前綴）:** ![Low][low_img] 所有 JavaScript 檔案中會用的 class（或 id）均以 `js-` 作為前綴區別，並且 CSS 不該套用樣式給所有含 `js-` 前綴，將 `js-` 保留只給 JavaScript 操作。

```html
<div id="js-slider" class="my-slider">
  <!-- Or -->
  <div id="id-used-by-cms" class="js-slider my-slider"></div>
</div>
```

- [ ] **embedded or inline CSS（CSS 的嵌入）:** ![High][high_img] 避免在  `<style>` 標籤內嵌 CSS 或使用行內 CSS，除非有正當理由（例如設定輪播圖的 `background-image` 或關鍵 CSS）。
- [ ] **Vendor prefixes（前綴產生器）:** ![High][high_img] 已經使用了 CSS 的 vendor prefixes，且依照瀏覽器支援與相容狀況自動生成相對應的 CSS 前綴。

- 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### CSS Performance

- [ ] **Concatenation（並列）:** ![High][high_img] CSS 檔案已合併為單一檔案（HTTP/2 不適用）。
- [ ] **Minification（最小化）:** ![High][high_img] 所有 CSS 檔案均已壓縮（Minified）。
- [ ] **Non-blocking（不阻塞）:** ![Medium][medium_img] CSS 檔案應設為非阻塞（non-blocking），避免還在抓取 DOM 時就載入。

- 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
- 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS（無用 CSS）:** ![Low][low_img] 移除沒用到的 CSS。

- 🛠 [UnCSS Online](https://uncss-online.com/)
- 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
- 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
- 🛠 [Chrome DevTools Coverage](https://developer.chrome.com/docs/devtools/coverage/)

### CSS 測試

- [ ] **Stylelint:** ![High][high_img] 檢測所有 CSS、SCSS 或樣式檔案都沒有錯誤。

- 🛠 [stylelint, a CSS linter](https://stylelint.io/)
- 📖 [Sass guidelines](https://sass-guidelin.es/)

- [ ] **Responsive web design（響應式設計）:** ![High][high_img] 所有頁面至少測試下列寬度斷點 320px, 768px, 1024px (可以依照你的客戶群進行增減)的**響應式測式**。

  - 🛠 [Am I Responsive?](http://ami.responsivedesign.is/)
  - 🛠 [Mobile Friendly Test](https://search.google.com/test/mobile-friendly)
  - 🛠 [Responsive Website Design Tester](https://responsivedesignchecker.com/)

- [ ] **CSS Validator（CSS 檢測）:** ![Medium][medium_img] 測試 CSS 並且修正相關錯誤。

- 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

- [ ] **Desktop Browsers （桌上瀏覽器）:** ![High][high_img] 所有頁面都經過所有桌上瀏覽器的測試（Safari, Firefox, Chrome, Internet Explorer, EDGE...）。
- [ ] **Mobile Browsers （手機瀏覽器）:** ![High][high_img] 所有頁面都經過所有手機瀏覽器的測試（Native browser, Chrome, Safari...）。
- [ ] **OS （作業系統）:** ![High][high_img] 所有頁面都經過所有作業系統的測試（Windows, Android, iOS, Mac...）。

- [ ] **Design fidelity （忠實呈現設計）:** ![Low][low_img] 根據專案需求與設計的品質，可能需要盡量貼近設計稿。你可以使用工具來比較設計稿與程式碼實作，盡量確保視覺的一致性。

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

- [ ] **Reading direction （閱讀方向）:** ![High][high_img] 如果有其他語系會被使用到的話，針對所有頁面都使用 LTR 跟 RTL 閱讀方向測試過。

- 📖
  [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
- 📖
  [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ 返回目錄](#目錄)**

---

## Images

> **補充：** 觀看 Addy Osmani 的免費電子書 **[Essential Image Optimization](https://images.guide/)** 以理解圖片的最佳化。

### 最佳實踐

- [ ] **Optimization（最佳化）:** ![High][high_img] 所有圖片均已最佳化，以確保在瀏覽器中順暢渲染。 關鍵頁面（如首頁）可考慮使用 WebP 格式以提升效能。

- 🛠 [Imagemin](https://github.com/imagemin/imagemin)
- 🛠 利用 [ImageOptim](https://imageoptim.com/) 免費最佳化您的圖片。
- 🛠 利用 [KeyCDN Image Processing](https://www.keycdn.com/support/image-processing) 用於即時圖片影像最佳化。
- 🛠 [TinyPNG](https://tinypng.com/) 最佳化 png、apng（動畫 png）和 jpg 圖像，品質損失很小。 提供免費和付費版本​​。
- 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) 使用 SVG 遮罩（masking）對透明圖片進行類似 JPG 的壓縮。
- 🛠 [SVGO](https://github.com/svg/svgo) 基於 Node.js 的工具，用於最佳化 SVG 向量圖片。
- 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/) 是 SVGO 的網頁版 GUI，可在線上最佳化您的 SVG 圖檔。

- [ ] **Picture/Srcset:** ![Medium][medium_img] 使用 `<picture>` 或 `srcset` 來提供最適合使用者當前 Viewport 的圖片。

- 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

- [ ] **Retina（視網膜螢幕）:** ![Low][low_img] 你有提供 2x 或 3x 解析度的版面圖片，以支援 Retina 顯示器。
- [ ] **Sprite（雪碧圖）:** ![Medium][medium_img] 小型圖片應使用 Sprite 檔案（圖示可使用 SVG Sprite）。
- [ ] **Width and Height（寬與高）:** ![High][high_img] 若已知最終渲染的圖片大小，應在 `<img>` 標籤上設定 `width` 和 `height` 屬性（若使用 CSS 控制大小則可省略）。
- [ ] **Alternative text（補充文字）:** ![High][high_img] 所有 `<img>` 標籤都應包含描述圖片內容的替代文字（Alt Text）。

- 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

- [ ] **Lazy loading（延遲載入）:** ![Medium][medium_img] 圖片應使用 Lazy Load 技術（並提供 noscript 無程式碼的備案）。
  - 🛠 [Native lazy loading polyfill](https://github.com/mfranzke/loading-attribute-polyfill/)

**[⬆ 返回目錄](#目錄)**

---

## JavaScript

### 最佳實踐

- [ ] **JavaScript Inline（HTML 中的行內 JS）:** ![High][high_img] 避免在 HTML 內嵌 JavaScript 程式碼（應將 JS 置於獨立檔案中）。
- [ ] **Concatenation（並列）:** ![High][high_img] JavaScript 檔案應進行合併（Concatenation）。
- [ ] **Minification（最小化）:** ![High][high_img] JavaScript 檔案應進行壓縮（Minification），並加上 .min 後綴標示。

- 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

- [ ] **JavaScript security（JavaScript 安全性）:** ![High][high_img]

- 📖
  [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

- [ ] **`noscript` tag:** ![Medium][medium_img] 在 HTML `<body>` 中使用 `<noscript>` 標籤，以應對瀏覽器不支援某些程式腳本類型或 JavaScript 被停用的情況。
這對於像 React.js 這類前端渲染密集的應用特別有幫助。可參考[範例](https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498).

```html
<noscript> You need to enable JavaScript to run this app. </noscript>
```

- [ ] **Non-blocking（不阻塞）:** ![Medium][medium_img] 使用 `async` 或 `defer` 屬性來非同步載入 JavaScript，減少渲染阻塞。

- 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

- [ ] **Optimized and updated JS libraries（更新並最佳化 JS 套件）:** ![Medium][medium_img] 確保你專案中所有 JavaScript 函式庫或套件皆為必要的，並將其更新至最新版本。對於簡單功能，建議使用 Vanilla JavaScript 以減少依賴。

- 📖 [You may not need jQuery](http://youmightnotneedjquery.com/)
- 📖 [Vanilla JavaScript for building powerful web applications](https://plainjs.com/)

- [ ] **Modernizr:** ![Low][low_img] 如果你需要指定特定的瀏覽器功能，可使用自訂的 Modernizr 為 <html> 標籤添加適當的類別。

- 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript 測試

- [ ] **ESLint:** ![High][high_img] 確保 ESLint 不報錯，並符合專案的設定或標準規則。

- 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ 返回目錄](#目錄)**

---

## Security 安全性

### 掃瞄並檢視你的網站

- [securityheaders.io](https://securityheaders.io/)
- [Observatory by Mozilla](https://observatory.mozilla.org/)

### 最佳實踐

- [ ] **HTTPS:** ![High][high_img] 所有頁面跟所有外部的內容（外掛、圖片...等）都使用 HTTPS

- 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
- 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
- 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

- [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] 在 HTTP header 設置 `Strict-Transport-Security`。

- 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
- 📖
  [HTTP Strict Transport Security Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
- 📖
  [Transport Layer Protection Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)

- [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] 確認發送到 Server Side 服務端的請求合法，且確實來自你的網站或 APP，避免 CSRF 攻擊。

- 📖
  [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)

- [ ] **Cross Site Scripting (XSS):** ![High][high_img] 確認網站或頁面不會發生 XSS 的情況。

- 📖
  [XSS (Cross Site Scripting) Prevention Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
- 📖
  [DOM based XSS Prevention Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html)

- [ ] **Content Type Options:** ![Medium][medium_img] 防止 Google Chrome 和 Internet Explorer 嘗試進行 MIME 嗅探，將伺服器聲明的 Content-Type 更改為其他類型。

- 📖
  [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

- [ ] **X-Frame-Options (XFO):** ![Medium][medium_img] 保護你的使用者免於點擊劫持（Clickjacking）攻擊。

- 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
- 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

- [ ] **Content Security Policy:** ![Medium][medium_img] 定義網站內容的加載方式及允許的來源，並可用於防範點擊劫持（Clickjacking）攻擊。

- 📖
  [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
- 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
- 📖 [CSP Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
- 📖 [Content Security Policy Reference](https://content-security-policy.com/)

**[⬆ 返回目錄](#目錄)**

---

## Performance 效能

### 最佳實踐

- [ ] **Goals to achieve（需要達成的目標）:** ![Medium][medium_img] 你的頁面應完成以下目標：

  - 首次有意義繪製（First Meaningful Paint） 在 1 秒內完成
  - 可互動時間（Time To Interactive, TTI）
    - 首次載入：在「一般」設備配置下 5 秒內完成（測試條件：$200 美元 Android 手機、慢速 3G 網路、400ms RTT、400kbps 傳輸速度）
    - 重複訪問：應在 2 秒內完成
  - 關鍵資源大小在 170KB（Gzip 壓縮後）以內

- 🛠 [Website Page Analysis](https://tools.pingdom.com)
- 🛠 [WebPageTest](https://www.webpagetest.org/)
- 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified HTML（最小化 HTML）:** ![Medium][medium_img] 你的 HTML 有進行壓縮。

- [ ] **Lazy loading（延遲仔入）:** ![Medium][medium_img] 讓圖片、程式腳本跟 CSS 都進行 lazy load 延遲載入，以提升當前瀏覽的網頁的反應速度（細節在它們個別的章節中）。

- [ ] **Cookie size（限制 cookie 的大小與數量）:** ![Medium][medium_img] 如果你有使用 cookie，確保 cookie 大小不要超過 4096 bytes，且在你的網域內別超過 20 個 cookie。

- 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
- 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
- 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

- [ ] **Third party components（第三方元件）:** ![Medium][medium_img] 盡可能以靜態元件取代第三方 iframe 或依賴外部 JS 的元件（如分享按鈕），進而限制呼叫外部 APIs 的次數並保護使用者的行動隱私。

- 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests 預先準備接下來的請求

- 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

- [ ] **DNS resolution（DNS 解析）:** ![Low][low_img] 使用 `dns-prefetch` 在閒置時間預先解析可能需要的第三方服務 DNS 服務。

```html
<link rel="dns-prefetch" href="https://example.com" />
```

- [ ] **Preconnection（預連接）:** ![Low][low_img] 使用 `preconnect` 在閒置時間提前完成 DNS 查詢、TCP 交握以及 TLS 協定即將要使用到的服務。

```html
<link rel="preconnect" href="https://example.com" />
```

- [ ] **Prefetching（預擷取）:** ![Low][low_img] 使用 `prefetch` 在閒置時間提前請求即將使用到的資源（例如 lazy loaded images）。

```html
<link rel="prefetch" href="image.png" />
```

- [ ] **Preloading（預載入）:** ![Low][low_img] 使用 `preload` 提前載入當前頁面需要的資源（例如放在 `<body>` 末尾的 `script` 腳本）。

```html
<link rel="preload" href="app.js" />
```

- 📖
  [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing 效能測試

- [ ] **Google PageSpeed:** ![High][high_img] 測試過所有的網頁（不只首頁）且分數都至少90分（滿分100）。

- 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
- 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
- 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)
- 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/)
- 🛠 [Speedrank - Improve the performance of your website](https://speedrank.app/)

**[⬆ 返回目錄](#目錄)**

## Accessibility 無障礙

> **補充：** 你也可以參考這份清單
> [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### 最佳實踐

- [ ] **Progressive enhancement:** ![Medium][medium_img] 網站的重要功能，像是主要的導覽指引或搜尋區塊，需要在沒有 JavaScript 的情況下也能運作。

- 📖 [在 Chrome 開發者工具啟用/停用 JavaScript](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] 色彩對比應至少符合 WCAG AA 標準（行動裝置建議達到 AAA 標準）。

- 🛠 [Contrast ratio](https://www.siegemedia.com/contrast-ratio)

#### Headings 標題

- [ ] **H1:** ![High][high_img] 所有頁面都要有一個不是網頁標題名稱的 H1 標籤（代表頁面的主要功能）。
- [ ] **Headings:** ![High][high_img] 標題標籤要按照合理的等級順序妥善使用（H1 to H6）。

- 📹
  [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

### Semantics 語意化

- [ ] **Specific HTML5 input types are used （有指定 HTML5 輸入標籤的類型）:** ![Medium][medium_img]  這對在手機上顯示不同類型的客製化鍵盤或配件特別重要。

- 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form 表單

- [ ] **Label:** ![High][high_img] Lable 各自會與相對的表單元素產生關聯。如果希望 label 不顯示，請使用 `aria-label` 來代替。

- 📖
  [使用 aria-label 屬性 - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### Accessibility testing 無障礙測試

- [ ] **Accessibility standards testing（無障礙標準測試）:** ![High][high_img] 利用 Wave 測試你的頁面是否符合無障礙標準。

- 🛠 [Wave testing](http://wave.webaim.org/)

- [ ] **Keyboard navigation （鍵盤導覽）:** ![High][high_img] 測試看看你的網站只使用鍵盤按照順序瀏覽，確保所有互動元素都可以點選使用。
- [ ] **Screen-reader （螢幕閱讀器）:** ![Medium][medium_img] 所有頁面都使用螢幕閱讀器測試過 (VoiceOver、ChromeVox、NVDA 或 Lynx)。
- [ ] **Focus style（焦點樣式）:** ![High][high_img] 如果 focus 焦點被停用，它將被 CSS 中的 `visible` 可見狀態取代。

- 📹
  [管理 Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ 返回目錄](#目錄)**

## SEO

- [ ] **Google Analytics:** ![Low][low_img] 確認 Google Analytics 已經安裝且確實的設定好。

- 🛠 [Google Analytics](https://analytics.google.com/analytics/web/)
- 🛠 [GA Checker (and others)](http://www.gachecker.com/)

- [ ] **Search Console:** ![Low][low_img] 已安裝並正確設定 Search Console。這是 Google 提供的免費服務，可幫助你監控、維護並排除網站在 Google 搜尋結果中的問題。

- 🛠 [Search Console](https://search.google.com/search-console/about)

- [ ] **Headings logic:** ![Medium][medium_img] Headings 有助於理解這個頁面的內容。

- 🛠 [Tota11y, tab Headings](http://khan.github.io/tota11y/#Try-it)

- [ ] **sitemap.xml:** ![High][high_img] 確認有 sitemap.xml 且已經提交給 Google Search Console（Google 搜尋引擎管理者，即之前的 Google 頁面管理者工具）。

- 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

- [ ] **robots.txt:** ![High][high_img] Robots.txt 不會破壞網頁。

- 🛠 利用 [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool) 測試你的robots.txt。

- [ ] **Structured Data（結構化資料）:** ![High][high_img] 確認所有頁面使用了結構化資料且已經測試過沒有出現錯誤。結構化資料會協助爬蟲理解這個頁面的內容。

- 📖 [介紹 Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
- 📖 [JSON-LD](https://json-ld.org/)
- 📖 [Microdata](https://www.w3.org/TR/microdata/)
- 🛠 利用 [Rich Results Test](https://search.google.com/test/rich-results) 測試你的網頁
- 🛠 適用於結構化資料的完整詞彙列表。[Schema.org Full Hierarchy](http://schema.org/docs/full.html)

- [ ] **Sitemap HTML:** ![Medium][medium_img] 已經設置 HTML sitemap 網站地圖，並且可以透過網站 footer 中的連結轉導進入。

- 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)

**[⬆ 返回目錄](#目錄)**

## Translations

前端待辦清單還有其他語言版本！感謝所有翻譯者的貢獻，你們的努力太棒了！

- 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
- 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
- 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
- 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
- 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
- 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
- 🇹🇼 Traditional Chinese: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)
- 🇫🇷 French: [ynizon/Front-End-Checklist](https://github.com/ynizon/Front-End-Checklist)
- 🇷🇺 Russian: [ungear/Front-End-Checklist](https://github.com/ungear/Front-End-Checklist)
- 🇹🇷 Turkish: [eraycetinay/Front-End-Checklist](https://github.com/eraycetinay/Front-End-Checklist)
- 🇩🇪 German: [xfuture603/Front-End-Checklist](https://github.com/xFuture603/Front-End-Checklist)
- 🇵🇱 Polish: [mbiesiad/Front-End-Checklist](https://github.com/mbiesiad/Front-End-Checklist)
- 🇮🇩 Indonesian: [nniinnoo/Front-End-Checklist](https://github.com/nniinnoo/Front-End-Checklist)

## Support

如果你有任何問題或建議，請隨時透過 X 與我聯繫：

- [X (formerly Twitter)](https://ddias.link/x)
- [Chat on Discord](https://ddias.link/discord)

## Contributors

這個專案的存在要感謝所有貢獻者！ ([Contribute](https://github.com/thedaviddias/Front-End-Checklist/blob/main/CONTRIBUTING.md)).
<a href="https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors"><img src="https://opencollective.com/front-end-checklist/contributors.svg?width=890" alt="Contributors" /></a>

## Backers

感謝所有支持我們的贊助者！ 🙏 [[成為贊助者](https://opencollective.com/front-end-checklist#backer)]

<a href="https://opencollective.com/front-end-checklist#backers" target="_blank"><img src="https://opencollective.com/front-end-checklist/backers.svg?width=890" alt="Backers" /></a>

## Sponsors

支持這個專案，成為贊助商！你的 Logo 標誌將顯示在此處並連結至您的網站。
[[成為贊助商](https://opencollective.com/front-end-checklist#sponsor)]

<a href="https://opencollective.com/front-end-checklist" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/1/avatar.svg" alt="Sponsors" /></a>

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ 返回目錄](#目錄)**

[low_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/low.svg
[medium_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/medium.svg
[high_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/high.svg
