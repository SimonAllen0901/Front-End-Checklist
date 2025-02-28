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
- [Webfonts](#webfonts)
- [CSS](#css)
- [Images](#images)
- [JavaScript](#javascript)
- [Security](#security)
- [Performance](#performance)
- [Accessibility](#accessibility)
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

- [ ] **Doctype （檔案類型）** ![High][high_img] Doctype 是 HTML5，需要放在 HTML 檔案內的最上面。

<!-- prettier-ignore-start -->
```html
<!doctype html><!-- HTML5 -->
```
<!-- prettier-ignore-end -->

- 📖
  [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

_而接下來 Charset 和 Viewport 這兩個 `<meta>` 標籤一定要放在 `<head>` 內的最前面！_

- [ ] **Charset:** ![High][high_img] 正確宣告字符編碼（UTF-8）。

<!-- prettier-ignore-start -->
```html
<!-- Set character encoding for the document -->
<meta charset="utf-8">
```
<!-- prettier-ignore-end -->

- [ ] **Viewport:** ![High][high_img] 正確宣告 viewport 設定。

<!-- prettier-ignore-start -->
```html
<!-- Viewport for responsive web design -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```
<!-- prettier-ignore-end -->

- [ ] **Title:** ![High][high_img] 所有頁面都要設定標題 （SEO: Google 會計算 title 上使用的字符寬度，只會偵測到 472px ~ 482px 之間。平均最大值是 55 個字符）

```html
<!-- Document Title -->
<title>Page Title less than 55 characters</title>
```

- 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
- 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

- [ ] **Description:** ![High][high_img] 有設置 meta description，每個頁面只有一個且長度不能超過150字元。

<!-- prettier-ignore-start -->
```html
<!-- Meta Description -->
<meta name="description" content="Description of the page less than 150 characters">
```
<!-- prettier-ignore-end -->

- 📖
  [Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

- [ ] **Favicons:** ![Medium][medium_img] 每一個 favicon 都需要創立且被正確展示。如果你只有一個 `favicon.ico`，可以將它置於網站的根目錄好讀取。通常你不需要對它設定。然而現在還是建議照下方的範例手動連結，以確保最佳實踐。現在比起 `.icon` 比較推薦 PNG 檔案格式。（大小最少需要: 32x32px）

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

- [ ] **Canonical:** ![Medium][medium_img] 使用 `rel="canonical"` 避免重複的內容。

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

### HTML tags

- [ ] **Language attribute:** ![High][high_img] The `lang` attribute of your website is specified and related to the
      language of the current page.

```html
<html lang="en"></html>
```

- [ ] **Direction attribute:** ![Medium][medium_img] The direction of lecture is specified on the html tag (It can be
      used on another HTML tag).

```html
<html dir="rtl">
  <!-- ... -->
</html>
```

- 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

- [ ] **Alternate language:** ![Low][low_img] The language tag of your website is specified and related to the language
      of the current page.

<!-- prettier-ignore-start -->
```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```
<!-- prettier-ignore-end -->

- [ ] **x-default:** ![Low][low_img] The language tag of your website for international landing pages.

```html
<link rel="alternate" href="https://example.com/" hreflang="x-default" />
```

- 📖 [x-default - Google](https://webmasters.googleblog.com/2013/04/x-default-hreflang-for-international-pages.html)

- [ ] **Conditional comments:** ![Low][low_img] Conditional comments are present for IE if needed.

- 📖
  [About conditional comments (Internet Explorer) - MSDN - Microsoft](<https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx>)

- [ ] **RSS feed:** ![Low][low_img] If your project is a blog or has articles, an RSS link was provided.

- [ ] **CSS Critical:** ![Medium][medium_img] The CSS critical (or "above the fold") collects all the CSS used to render
      the visible portion of the page. It is embedded before your principal CSS call and between `<style></style>` in a
      single line (minified).

- 🛠 [Critical by Addy Osmani on GitHub](https://github.com/addyosmani/critical) automates this.

- [ ] **CSS order:** ![High][high_img] All CSS files are loaded before any JavaScript files in the `<head>`. (Except the
      case where sometimes JS files are loaded asynchronously on top of your page).

### Social meta

Visualize and generate automatically our social meta tags with [Meta Tags](https://metatags.io/)

**_Facebook OG_** and **_Twitter Cards_** are, for any website, highly recommended. The other social media tags can be
considered if you target a particular presence on those and want to ensure the display.

- [ ] **Facebook Open Graph:** ![Low][low_img] All Facebook Open Graph (OG) are tested and no one is missing or with
      false information. Images need to be at least 600 x 315 pixels, although 1200 x 630 pixels is recommended.

<!-- prettier-ignore-start -->
> [!NOTE]
> Using `og:image:width` and `og:image:height` will specify the image dimensions to the crawler so that it can render the image immediately without having to asynchronously download and process it.
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
- 🛠 Test your page with the [Facebook OG testing](https://developers.facebook.com/tools/debug/)

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
- 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ back to top](#-table-of-contents)**

## HTML

### 最佳實踐

- [ ] **HTML5 Semantic Elements:** ![High][high_img] HTML5 Semantic Elements are used appropriately (header, section,
      footer, main...).

- 📖 [HTML Reference](http://htmlreference.io/)

- [ ] **Error pages:** ![High][high_img] Error 404 page and 5xx exist. Remember that the 5xx error pages need to have
      their CSS integrated (no external call on the current server).

- [ ] **Noopener:** ![Medium][medium_img] In case you are using external links with `target="_blank"`, your link should
      have a `rel="noopener"` attribute to prevent tab nabbing. If you need to support older versions of Firefox, use
      `rel="noopener noreferrer"`.

- 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

- [ ] **Clean up comments:** ![Low][low_img] Unnecessary code needs to be removed before sending the page to production.

### HTML testing

- [ ] **W3C compliant:** ![High][high_img] All pages need to be tested with the W3C validator to identify possible
      issues in the HTML code.

- 🛠 [W3C validator](https://validator.w3.org/)

- [ ] **HTML Lint:** ![High][high_img] I use tools to help me analyze any issues I could have on my HTML code.

- 🛠 [Dirty markup](https://www.10bestdesign.com/dirtymarkup/)

- 🛠 [webhint](https://webhint.io/)

- [ ] **Link checker:** ![High][high_img] There are no broken links in my page, verify that you don't have any 404
      error.

- 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

- [ ] **Adblockers test:** ![Medium][medium_img] Your website shows your content correctly with adblockers enabled (You
      can provide a message encouraging people to disable their adblocker).

- 📖
  [Use AdBlocking in your Dev Environment](https://andreicioara.com/use-adblocking-in-your-dev-environment-48db500d9b86)

**[⬆ back to top](#-table-of-contents)**

---

## Webfonts

> [!NOTE]
> Using web fonts may cause Flash Of Unstyled Text/Flash Of Invisible Text - consider having fallback fonts
> and/or utilizing web font loaders to control behavior.

- 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

- [ ] **Webfont format:** ![High][high_img] WOFF, WOFF2 and TTF are supported by all modern browsers.

- 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/woff).
- 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/woff2).
- 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/ttf)
- 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

- [ ] **Webfont size:** ![High][high_img] Webfont sizes don't exceed 2 MB (all variants included).

- [ ] **Webfont loader:** ![Low][low_img] Control loading behavior with a webfont loader

- 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ back to top](#-table-of-contents)**

---

## CSS

> **Notes:** Take a look at [CSS guidelines](https://cssguidelin.es/) and [Sass Guidelines](https://sass-guidelin.es/)
> followed by most Front-End developers. If you have a doubt about CSS properties, you can visit
> [CSS Reference](http://cssreference.io/). There is also a short [Code Guide](http://codeguide.co/) for consistency.

- [ ] **Responsive Web Design:** ![High][high_img] The website is using responsive web design.
- [ ] **CSS Print:** ![Medium][medium_img] A print stylesheet is provided and is correct on each page.
- [ ] **Preprocessors:** ![Low][low_img] Your project is using a CSS preprocessor (e.g [Sass](http://sass-lang.com/),
      [Less](http://lesscss.org/), [Stylus](http://stylus-lang.com/)).
- [ ] **Unique ID:** ![High][high_img] If IDs are used, they are unique to a page.
- [ ] **Reset CSS:** ![High][high_img] A CSS reset (reset, normalize or reboot) is used and up to date. _(If you are
      using a CSS Framework like Bootstrap or Foundation, a Normalize is already included into it.)_

- 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
- 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
- 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

- [ ] **JS prefix:** ![Low][low_img] All classes (or id- used in JavaScript files) begin with **js-** and are not styled
      into the CSS files.

```html
<div id="js-slider" class="my-slider">
  <!-- Or -->
  <div id="id-used-by-cms" class="js-slider my-slider"></div>
</div>
```

- [ ] **embedded or inline CSS:** ![High][high_img] Avoid at all cost embedding CSS in `<style>` tags or using inline
      CSS: only use for valid reasons (e.g. background-image for slider, critical CSS).
- [ ] **Vendor prefixes:** ![High][high_img] CSS vendor prefixes are used and are generated accordingly with your
      browser support compatibility.

- 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### CSS Performance

- [ ] **Concatenation:** ![High][high_img] CSS files are concatenated in a single file _(Not for HTTP/2)_.
- [ ] **Minification:** ![High][high_img] All CSS files are minified.
- [ ] **Non-blocking:** ![Medium][medium_img] CSS files need to be non-blocking to prevent the DOM from taking time to
      load.

- 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
- 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Low][low_img] Remove unused CSS.

- 🛠 [UnCSS Online](https://uncss-online.com/)
- 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
- 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
- 🛠 [Chrome DevTools Coverage](https://developer.chrome.com/docs/devtools/coverage/)

### CSS testing

- [ ] **Stylelint:** ![High][high_img] All CSS or SCSS files are without any errors.

- 🛠 [stylelint, a CSS linter](https://stylelint.io/)
- 📖 [Sass guidelines](https://sass-guidelin.es/)

- [ ] **Responsive web design:** ![High][high_img] All pages were tested at the following breakpoints: 320px, 768px,
      1024px (can be more / different according to your analytics). **Responsive Checker -**

  - 🛠 [Am I Responsive?](http://ami.responsivedesign.is/)
  - 🛠 [Mobile Friendly Test](https://search.google.com/test/mobile-friendly)
  - 🛠 [Responsive Website Design Tester](https://responsivedesignchecker.com/)

- [ ] **CSS Validator:** ![Medium][medium_img] The CSS was tested and pertinent errors were corrected.

- 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

- [ ] **Desktop Browsers:** ![High][high_img] All pages were tested on all current desktop browsers (Safari, Firefox,
      Chrome, Internet Explorer, EDGE...).
- [ ] **Mobile Browsers:** ![High][high_img] All pages were tested on all current mobile browsers (Native browser,
      Chrome, Safari...).
- [ ] **OS:** ![High][high_img] All pages were tested on all current OS (Windows, Android, iOS, Mac...).

- [ ] **Design fidelity:** ![Low][low_img] Depending on the project and the quality of the creatives, you may be asked
      to be close to the design. You can use some tools to compare creatives with your code implementation and ensure
      consistency.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

- [ ] **Reading direction:** ![High][high_img] All pages need to be tested for LTR and RTL languages if they need to be
      supported.

- 📖
  [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
- 📖
  [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#-table-of-contents)**

---

## Images

> **Notes:** For a complete understanding of image optimization, check the free ebook
> **[Essential Image Optimization](https://images.guide/)** from Addy Osmani.

### 最佳實踐

- [ ] **Optimization:** ![High][high_img] All images are optimized to be rendered in the browser. WebP format could be
      used for critical pages (like Homepage).

- 🛠 [Imagemin](https://github.com/imagemin/imagemin)
- 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.
- 🛠 Use [KeyCDN Image Processing](https://www.keycdn.com/support/image-processing) for image optimization in real time.
- 🛠 [TinyPNG](https://tinypng.com/) optimises png, apng (animated png) and jpg images with very small loss in quality.
  Free and paid version available.
- 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) jpg-like compression for transparent images using svg masking.
- 🛠 [SVGO](https://github.com/svg/svgo) a Nodejs-based tool for optimizing SVG vector graphics files.
- 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/) a web-based GUI version of SVGO for optimising your svgs online.

- [ ] **Picture/Srcset:** ![Medium][medium_img] You use picture/srcset to provide the most appropriate image for the
      current viewport of the user.

- 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

- [ ] **Retina:** ![Low][low_img] You provide layout images 2x or 3x, support retina display.
- [ ] **Sprite:** ![Medium][medium_img] Small images are in a sprite file (in the case of icons, they can be in an SVG
      sprite image).
- [ ] **Width and Height:** ![High][high_img] Set `width` and `height` attributes on `<img>` if the final rendered image
      size is known (can be omitted for CSS sizing).
- [ ] **Alternative text:** ![High][high_img] All `<img>` have an alternative text which describes the image visually.

- 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

- [ ] **Lazy loading:** ![Medium][medium_img] Images are lazyloaded (A noscript fallback is always provided).
  - 🛠 [Native lazy loading polyfill](https://github.com/mfranzke/loading-attribute-polyfill/)

**[⬆ back to top](#-table-of-contents)**

---

## JavaScript

### 最佳實踐

- [ ] **JavaScript Inline:** ![High][high_img] You don't have any JavaScript code inline (mixed with your HTML code).
- [ ] **Concatenation:** ![High][high_img] JavaScript files are concatenated.
- [ ] **Minification:** ![High][high_img] JavaScript files are minified (you can add the `.min` suffix).

- 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

- [ ] **JavaScript security:** ![High][high_img]

- 📖
  [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

- [ ] **`noscript` tag:** ![Medium][medium_img] Use `<noscript>` tag in the HTML body if a script type on the page is
      unsupported or if scripting is currently turned off in the browser. This will be helpful in client-side rendering
      heavy apps such as React.js, see
      [examples](https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498).

```html
<noscript> You need to enable JavaScript to run this app. </noscript>
```

- [ ] **Non-blocking:** ![Medium][medium_img] JavaScript files are loaded asynchronously using `async` or deferred using
      `defer` attribute.

- 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

- [ ] **Optimized and updated JS libraries:** ![Medium][medium_img] All JavaScript libraries used in your project are
      necessary (prefer Vanilla Javascript for simple functionalities), updated to their latest version and don't
      overwhelm your JavaScript with unnecessary methods.

- 📖 [You may not need jQuery](http://youmightnotneedjquery.com/)
- 📖 [Vanilla JavaScript for building powerful web applications](https://plainjs.com/)

- [ ] **Modernizr:** ![Low][low_img] If you need to target some specific features you can use a custom Modernizr to add
      classes in your `<html>` tag.

- 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

- [ ] **ESLint:** ![High][high_img] No errors are flagged by ESLint (based on your configuration or standards rules).

- 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ back to top](#-table-of-contents)**

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

**[⬆ back to top](#-table-of-contents)**

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

- [ ] **Minified HTML:** ![Medium][medium_img] 你的 HTML 有進行壓縮。

- [ ] **Lazy loading:** ![Medium][medium_img] 讓圖片、程式腳本跟 CSS 都進行 lazy load 延遲載入，以提升當前瀏覽的網頁的反應速度（細節在它們個別的章節中）。

- [ ] **Cookie size:** ![Medium][medium_img] 如果你有使用 cookie，確保 cookie 大小不要超過 4096 bytes，且在你的網域內別超過 20 個 cookie。

- 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
- 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
- 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

- [ ] **Third party components:** ![Medium][medium_img] 盡可能以靜態元件取代第三方 iframe 或依賴外部 JS 的元件（如分享按鈕），進而限制呼叫外部 APIs 的次數並保護使用者的行動隱私。

- 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests 預先準備接下來的請求

- 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

- [ ] **DNS resolution:** ![Low][low_img] 使用 `dns-prefetch` 在閒置時間預先解析可能需要的第三方服務 DNS 服務。

```html
<link rel="dns-prefetch" href="https://example.com" />
```

- [ ] **Preconnection:** ![Low][low_img] 使用 `preconnect` 在閒置時間提前完成 DNS 查詢、TCP 交握以及 TLS 協定即將要使用到的服務。

```html
<link rel="preconnect" href="https://example.com" />
```

- [ ] **Prefetching:** ![Low][low_img] 使用 `prefetch` 在閒置時間提前請求即將使用到的資源（例如 lazy loaded images）。.

```html
<link rel="prefetch" href="image.png" />
```

- [ ] **Preloading:** ![Low][low_img] 使用 `preload` 提前載入當前頁面需要的資源（例如放在 `<body>` 末尾的 `script` 腳本）。

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

**[⬆ back to top](#-table-of-contents)**

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

- [ ] **Specific HTML5 input types are used （有指定 HTML5 輸入標籤的類型）** ![Medium][medium_img]  這對在手機上顯示不同類型的客製化鍵盤或配件特別重要。

- 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form 表單

- [ ] **Label:** ![High][high_img] Lable 各自會與相對的表單元素產生關聯。如果希望 label 不顯示，請使用 `aria-label` 來代替。

- 📖
  [使用 aria-label 屬性 - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### Accessibility testing 無障礙測試

- [ ] **Accessibility standards testing:** ![High][high_img] 利用 Wave 測試你的頁面是否符合無障礙標準。

- 🛠 [Wave testing](http://wave.webaim.org/)

- [ ] **Keyboard navigation （鍵盤導覽）** ![High][high_img] 測試看看你的網站只使用鍵盤按照順序瀏覽，確保所有互動元素都可以點選使用。
- [ ] **Screen-reader （螢幕閱讀器）** ![Medium][medium_img] 所有頁面都使用螢幕閱讀器測試過 (VoiceOver、ChromeVox、NVDA 或 Lynx)。
- [ ] **Focus style:** ![High][high_img] 如果 focus 焦點被停用，它將被 CSS 中的 `visible` 可見狀態取代。

- 📹
  [管理 Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#-table-of-contents)**

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

**[⬆ back to top](#-table-of-contents)**

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

**[⬆ back to top](#-table-of-contents)**

[low_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/low.svg
[medium_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/medium.svg
[high_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/high.svg
