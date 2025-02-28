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
- 📖 [Best Practices - Sharing](https://developers.facebook.com/docs/sharing/best-practices/)
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

### Best practices

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

### Best practices

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

### Best practices

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

## Security

### Scan and check your web site

- [securityheaders.io](https://securityheaders.io/)
- [Observatory by Mozilla](https://observatory.mozilla.org/)

### Best practices

- [ ] **HTTPS:** ![High][high_img] HTTPS is used on every page and for all external content (plugins, images...).

- 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
- 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
- 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

- [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] The HTTP header is set to
      'Strict-Transport-Security'.

- 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
- 📖
  [HTTP Strict Transport Security Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
- 📖
  [Transport Layer Protection Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)

- [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] You ensure that requests made to your server-side are
      legitimate and originate from your website / app to prevent CSRF attacks.

- 📖
  [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)

- [ ] **Cross Site Scripting (XSS):** ![High][high_img] Your page or website is free from XSS possible issues.

- 📖
  [XSS (Cross Site Scripting) Prevention Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
- 📖
  [DOM based XSS Prevention Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html)

- [ ] **Content Type Options:** ![Medium][medium_img] Prevents Google Chrome and Internet Explorer from trying to
      mime-sniff the content-type of a response away from the one being declared by the server.

- 📖
  [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

- [ ] **X-Frame-Options (XFO):** ![Medium][medium_img] Protects your visitors against clickjacking attacks.

- 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
- 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

- [ ] **Content Security Policy:** ![Medium][medium_img] Defines how content is loaded on your site and from where it is
      permitted to be loaded. Can also be used to protect against clickjacking attacks.

- 📖
  [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
- 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
- 📖 [CSP Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
- 📖 [Content Security Policy Reference](https://content-security-policy.com/)

**[⬆ back to top](#-table-of-contents)**

---

## Performance

### Best practices

- [ ] **Goals to achieve:** ![Medium][medium_img] Your pages should reach these goals:

  - First Meaningful Paint under 1 second
  - Time To Interactive under 5 seconds for the "average" configuration (a $200 Android on a slow 3G network with 400ms
    RTT and 400kbps transfer speed) and under 2 seconds for repeat visits
  - Critical file size under 170Kb gzipped

- 🛠 [Website Page Analysis](https://tools.pingdom.com)
- 🛠 [WebPageTest](https://www.webpagetest.org/)
- 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified HTML:** ![Medium][medium_img] Your HTML is minified.

- [ ] **Lazy loading:** ![Medium][medium_img] Images, scripts and CSS need to be lazy loaded to improve the response
      time of the current page (See details in their respective sections).

- [ ] **Cookie size:** ![Medium][medium_img] If you are using cookies be sure each cookie doesn't exceed 4096 bytes and
      your domain name doesn't have more than 20 cookies.

- 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
- 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
- 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

- [ ] **Third party components:** ![Medium][medium_img] Third party iframes or components relying on external JS (like
      sharing buttons) are replaced by static components when possible, thus limiting calls to external APIs and keeping
      your user's activity private.

- 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests

- 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

- [ ] **DNS resolution:** ![Low][low_img] DNS of third-party services that may be needed are resolved in advance during
      idle time using `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com" />
```

- [ ] **Preconnection:** ![Low][low_img] DNS lookup, TCP handshake and TLS negotiation with services that will be needed
      soon is done in advance during idle time using `preconnect`.

```html
<link rel="preconnect" href="https://example.com" />
```

- [ ] **Prefetching:** ![Low][low_img] Resources that will be needed soon (e.g. lazy loaded images) are requested in
      advance during idle time using `prefetch`.

```html
<link rel="prefetch" href="image.png" />
```

- [ ] **Preloading:** ![Low][low_img] Resources needed in the current page (e.g. scripts placed at the end of `<body>`)
      in advance using `preload`.

```html
<link rel="preload" href="app.js" />
```

- 📖
  [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

- [ ] **Google PageSpeed:** ![High][high_img] All your pages were tested (not only the homepage) and have a score of at
      least 90/100.

- 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
- 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
- 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)
- 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/)
- 🛠 [Speedrank - Improve the performance of your website](https://speedrank.app/)

**[⬆ back to top](#-table-of-contents)**

## Accessibility

> **Notes:** You can watch the playlist
> [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Best practices

- [ ] **Progressive enhancement:** ![Medium][medium_img] Major functionality like main navigation and search should work
      without JavaScript enabled.

- 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] Color contrast should at least pass WCAG AA (AAA for mobile).

- 🛠 [Contrast ratio](https://www.siegemedia.com/contrast-ratio)

#### Headings

- [ ] **H1:** ![High][high_img] All pages have an H1 which is not the title of the website.
- [ ] **Headings:** ![High][high_img] Headings should be used properly and in the right order (H1 to H6).

- 📹
  [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

### Semantics

- [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] This is especially important for mobile devices
      that show customized keypads and widgets for different types.

- 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

- [ ] **Label:** ![High][high_img] A label is associated with each input form element. In case a label can't be
      displayed, use `aria-label` instead.

- 📖
  [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### Accessibility testing

- [ ] **Accessibility standards testing:** ![High][high_img] Use the WAVE tool to test if your page respects the
      accessibility standards.

- 🛠 [Wave testing](http://wave.webaim.org/)

- [ ] **Keyboard navigation:** ![High][high_img] Test your website using only your keyboard in a previsible order. All
      interactive elements are reachable and usable.
- [ ] **Screen-reader:** ![Medium][medium_img] All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or
      Lynx).
- [ ] **Focus style:** ![High][high_img] If the focus is disabled, it is replaced by visible state in CSS.

- 📹
  [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#-table-of-contents)**

## SEO

- [ ] **Google Analytics:** ![Low][low_img] Google Analytics is installed and correctly configured.

- 🛠 [Google Analytics](https://analytics.google.com/analytics/web/)
- 🛠 [GA Checker (and others)](http://www.gachecker.com/)

- [ ] **Search Console:** ![Low][low_img] Search Console is installed and correctly configured. It is a free service
      offered by Google that helps you monitor, maintain, and troubleshoot your site's presence in Google Search
      results.

- 🛠 [Search Console](https://search.google.com/search-console/about)

- [ ] **Headings logic:** ![Medium][medium_img] Heading text helps to understand the content in the current page.

- 🛠 [Tota11y, tab Headings](http://khan.github.io/tota11y/#Try-it)

- [ ] **sitemap.xml:** ![High][high_img] A sitemap.xml exists and was submitted to Google Search Console (previously
      Google Webmaster Tools).

- 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

- [ ] **robots.txt:** ![High][high_img] The robots.txt is not blocking webpages.

- 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

- [ ] **Structured Data:** ![High][high_img] Pages using structured data are tested and are without errors. Structured
      data helps crawlers understand the content in the current page.

- 📖
  [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
- 📖 [JSON-LD](https://json-ld.org/)
- 📖 [Microdata](https://www.w3.org/TR/microdata/)
- 🛠 Test your page with the [Rich Results Test](https://search.google.com/test/rich-results)
- 🛠 Complete list of vocabularies that can be used as structured data.
  [Schema.org Full Hierarchy](http://schema.org/docs/full.html)

- [ ] **Sitemap HTML:** ![Medium][medium_img] An HTML sitemap is provided and is accessible via a link in the footer of
      your website.

- 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)

**[⬆ back to top](#-table-of-contents)**

## Translations

The Front-End Checklist is also available in other languages. Thanks for all translators and their awesome work!

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

If you have any question or suggestion, don't hesitate to reach me on X:

- [X (formerly Twitter)](https://ddias.link/x)
- [Chat on Discord](https://ddias.link/discord)

## Contributors

This project exists thanks to all the people who contribute. ([Contribute](https://github.com/thedaviddias/Front-End-Checklist/blob/main/CONTRIBUTING.md)).
<a href="https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors"><img src="https://opencollective.com/front-end-checklist/contributors.svg?width=890" alt="Contributors" /></a>

## Backers

Thank you to all our backers! 🙏 [[Become a backer](https://opencollective.com/front-end-checklist#backer)]

<a href="https://opencollective.com/front-end-checklist#backers" target="_blank"><img src="https://opencollective.com/front-end-checklist/backers.svg?width=890" alt="Backers" /></a>

## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website.
[[Become a sponsor](https://opencollective.com/front-end-checklist#sponsor)]

<a href="https://opencollective.com/front-end-checklist" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/1/avatar.svg" alt="Sponsors" /></a>

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#-table-of-contents)**

[low_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/low.svg
[medium_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/medium.svg
[high_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/high.svg
