<style>
:root {
  --page-bg: #ffffff;
  --gutter-bg: #2f2f2f;
  --text: #2d2926;
  --muted: #6d655f;
  --rule: #8a2f2f;
  --soft-rule: #ddd6d0;
  --link: #7b2929;
  --link-hover: #4f1717;
  --quote-bg: #faf8f6;
  --quote-text: #4f4945;
  --footnote-text: #554f4b;
  --media-bg: #f6f3f0;
  --control-bg: #ffffff;
  --control-hover: #f5f1ee;
  --control-active-bg: #7b2929;
  --control-active-text: #ffffff;
}

html,
body {
  min-height: 100%;
  background-color: var(--gutter-bg);
}

body {
  margin: 0;
  color: var(--text);
}

/* White book page with charcoal gutters extending to the browser edges. */
.markdown-body {
  --reader-measure: 820px;
  --reader-font-size: 18px;
  --reader-line-height: 1.68;
  --reader-font: Georgia, "Times New Roman", serif;

  width: 100%;
  max-width: 1200px !important;
  min-height: 100vh;
  margin: 0 auto !important;
  padding: 3rem 5rem 5rem !important;
  box-sizing: border-box;
  background-color: var(--page-bg);
  color: var(--text);
  font-family: var(--reader-font);
  font-size: var(--reader-font-size);
  line-height: var(--reader-line-height);
  box-shadow: 0 0 24px rgba(0, 0, 0, 0.18);
}

/* Reader-controlled typography and line length. */
.markdown-body[data-reader-size="small"] {
  --reader-font-size: 16px;
}

.markdown-body[data-reader-size="large"] {
  --reader-font-size: 20px;
}

.markdown-body[data-reader-size="xlarge"] {
  --reader-font-size: 22px;
}

.markdown-body[data-reader-width="narrow"] {
  --reader-measure: 680px;
}

.markdown-body[data-reader-width="wide"] {
  --reader-measure: 960px;
}

.markdown-body[data-reader-spacing="compact"] {
  --reader-line-height: 1.5;
}

.markdown-body[data-reader-spacing="spacious"] {
  --reader-line-height: 1.9;
}

.markdown-body[data-reader-font="sans"] {
  --reader-font: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
}

/* Optional reading themes. */
.markdown-body[data-reader-theme="paper"] {
  --page-bg: #f4efe4;
  --text: #332f2b;
  --muted: #746b62;
  --soft-rule: #d4c8b8;
  --quote-bg: #ece4d6;
  --quote-text: #4c453e;
  --footnote-text: #5b534c;
  --media-bg: #eee6d9;
  --control-bg: #fbf7ef;
  --control-hover: #eee5d7;
  color-scheme: light;
}

.markdown-body[data-reader-theme="dark"] {
  --page-bg: #20201f;
  --text: #eee9e2;
  --muted: #bcb3aa;
  --rule: #cf7373;
  --soft-rule: #504b46;
  --link: #e4a0a0;
  --link-hover: #f2c1c1;
  --quote-bg: #2a2826;
  --quote-text: #ddd6cf;
  --footnote-text: #cbc2b9;
  --media-bg: #292725;
  --control-bg: #2b2927;
  --control-hover: #373431;
  --control-active-bg: #a94f4f;
  --control-active-text: #ffffff;
  color-scheme: dark;
}

html[data-reader-theme="paper"],
html[data-reader-theme="paper"] body {
  background-color: #37332f;
}

html[data-reader-theme="dark"],
html[data-reader-theme="dark"] body {
  background-color: #151515;
}

/* Keep prose at a comfortable book-like measure while allowing images to breathe. */
.markdown-body > p,
.markdown-body > ul,
.markdown-body > ol,
.markdown-body > blockquote,
.markdown-body > h2,
.markdown-body > h3,
.markdown-body > pre,
.markdown-body > table,
.markdown-body > .footnotes {
  max-width: var(--reader-measure);
  margin-left: auto;
  margin-right: auto;
}

.markdown-body p {
  margin-top: 0;
  margin-bottom: 1.15em;
}

/* GitHub Pages/Jekyll site title: "Arkansas Créole." */
.markdown-body > h1:first-of-type {
  max-width: 820px;
  margin: 0 auto 0.4rem;
  padding: 0;
  border-bottom: 0 !important;
  color: var(--text);
  font-family: var(--reader-font);
  font-size: 2.75rem;
  font-weight: 600;
  line-height: 1.08;
  letter-spacing: 0.055em;
  text-align: center;
  font-variant-caps: small-caps;
  font-variant: small-caps;
  text-transform: none;
}

.markdown-body > h1:first-of-type a {
  color: inherit !important;
  text-decoration: none !important;
}

.book-title-block {
  max-width: 820px;
  margin: 0 auto 3.6rem;
  padding-bottom: 0.1rem;
  text-align: center;
}

.book-title-block::after {
  content: "";
  display: block;
  width: 88px;
  height: 3px;
  margin: 2rem auto 0;
  background: var(--rule);
}

.book-title-block .book-subtitle {
  margin: 0.75rem auto 0.7rem;
  font-size: 1.17rem;
  line-height: 1.45;
}

.book-title-block .book-kicker {
  margin: 0.35rem auto;
  color: var(--muted);
  font-size: 1.02rem;
}

.book-title-block .book-author {
  margin: 0.95rem auto 0;
  font-size: 1.02rem;
  letter-spacing: 0.02em;
}

/* Kindle-style reading settings: compact, persistent, and keyboard accessible. */
.reader-settings-wrap {
  position: sticky;
  top: 0.75rem;
  z-index: 50;
  display: flex;
  justify-content: flex-end;
  max-width: 980px;
  margin: -1.8rem auto 2.5rem;
  pointer-events: none;
}

.reader-settings {
  position: relative;
  pointer-events: auto;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  font-size: 14px;
  line-height: 1.35;
}

.reader-settings > summary {
  display: flex;
  align-items: center;
  gap: 0.45rem;
  padding: 0.55rem 0.75rem;
  border: 1px solid var(--soft-rule);
  border-radius: 999px;
  background: var(--control-bg);
  color: var(--text);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.10);
  cursor: pointer;
  list-style: none;
  user-select: none;
}

.reader-settings > summary::-webkit-details-marker {
  display: none;
}

.reader-settings > summary::marker {
  content: "";
}

.reader-settings > summary:hover {
  background: var(--control-hover);
}

.reader-settings > summary:focus-visible,
.reader-setting-button:focus-visible,
.reader-settings-reset:focus-visible {
  outline: 2px solid var(--rule);
  outline-offset: 2px;
}

.reader-settings[open] > summary {
  background: var(--control-hover);
}

.reader-settings-aa {
  font-family: Georgia, "Times New Roman", serif;
  font-size: 1.05rem;
  font-weight: 700;
  letter-spacing: -0.03em;
}

.reader-settings-panel {
  position: absolute;
  top: calc(100% + 0.55rem);
  right: 0;
  width: 330px;
  max-width: calc(100vw - 2.5rem);
  padding: 1rem;
  border: 1px solid var(--soft-rule);
  border-radius: 0.8rem;
  background: var(--control-bg);
  color: var(--text);
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.18);
}

.reader-settings-panel fieldset {
  margin: 0 0 0.95rem;
  padding: 0;
  border: 0;
}

.reader-settings-panel legend {
  margin-bottom: 0.4rem;
  padding: 0;
  color: var(--muted);
  font-size: 0.76rem;
  font-weight: 700;
  letter-spacing: 0.045em;
  text-transform: uppercase;
}

.reader-options {
  display: flex;
  flex-wrap: wrap;
  gap: 0.35rem;
}

.reader-setting-button,
.reader-settings-reset {
  appearance: none;
  -webkit-appearance: none;
  border: 1px solid var(--soft-rule);
  border-radius: 0.45rem;
  background: transparent;
  color: var(--text);
  font: inherit;
  cursor: pointer;
}

.reader-setting-button {
  min-width: 2.55rem;
  padding: 0.42rem 0.58rem;
}

.reader-setting-button:hover,
.reader-settings-reset:hover {
  background: var(--control-hover);
}

.reader-setting-button[aria-pressed="true"] {
  border-color: var(--control-active-bg);
  background: var(--control-active-bg);
  color: var(--control-active-text);
}

.reader-settings-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.75rem;
  margin-top: 0.2rem;
  padding-top: 0.8rem;
  border-top: 1px solid var(--soft-rule);
}

.reader-settings-note {
  margin: 0 !important;
  color: var(--muted);
  font-size: 0.74rem;
  line-height: 1.35;
}

.reader-settings-reset {
  flex: 0 0 auto;
  padding: 0.38rem 0.55rem;
}

.sr-only {
  position: absolute !important;
  width: 1px !important;
  height: 1px !important;
  padding: 0 !important;
  margin: -1px !important;
  overflow: hidden !important;
  clip: rect(0, 0, 0, 0) !important;
  white-space: nowrap !important;
  border: 0 !important;
}

/* Section headings: restrained, book-like, with a short burgundy rule. */
.markdown-body h2 {
  margin-top: 4.25rem;
  margin-bottom: 1.5rem;
  padding: 0;
  border-bottom: 0 !important;
  color: var(--text);
  font-family: var(--reader-font);
  font-size: 1.8rem;
  font-weight: 600;
  line-height: 1.25;
}

.markdown-body h2::after {
  content: "";
  display: block;
  width: 72px;
  height: 2px;
  margin-top: 0.7rem;
  background: var(--rule);
}

.markdown-body h3 {
  margin-top: 3.4rem;
  margin-bottom: 1.15rem;
  padding-top: 1.15rem;
  border-top: 1px solid var(--soft-rule);
  color: var(--text);
  font-family: var(--reader-font);
  font-size: 1.4rem;
  font-weight: 600;
  line-height: 1.32;
}

/* Contents page. */
#contents + h2 {
  margin-top: 0;
}

#contents + h2 + ul {
  max-width: calc(var(--reader-measure) + 40px);
  padding-left: 1.35rem;
  line-height: 1.52;
}

#contents + h2 + ul > li {
  margin: 0.45rem 0;
}

#contents + h2 + ul ul {
  margin-top: 0.3rem;
  margin-bottom: 0.55rem;
}

/* Links use a muted historical-book accent instead of GitHub blue. */
.markdown-body a {
  color: var(--link);
  text-decoration-color: color-mix(in srgb, var(--link) 35%, transparent);
  text-underline-offset: 0.12em;
}

/* Fallback for browsers without color-mix(). */
@supports not (color: color-mix(in srgb, red 50%, white)) {
  .markdown-body a {
    text-decoration-color: rgba(123, 41, 41, 0.35);
  }
}

.markdown-body a:hover,
.markdown-body a:focus {
  color: var(--link-hover);
  text-decoration-color: currentColor;
}

.markdown-body a[href="#contents"] {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  font-size: 0.76rem;
  font-weight: 600;
  letter-spacing: 0.055em;
  text-decoration: none;
  text-transform: uppercase;
}

/* Figures can be wider than the prose column. */
.markdown-body > figure {
  max-width: 980px;
  margin: 2.6rem auto 3rem;
}

.markdown-body figure img,
.markdown-body > p > img {
  display: block;
  max-width: 100%;
  height: auto;
  margin: 0 auto;
}

.markdown-body figcaption {
  max-width: 850px;
  margin: 0.85rem auto 0;
  color: var(--muted);
  font-size: 0.84rem;
  font-style: italic;
  line-height: 1.5;
  text-align: center;
}

.markdown-body figure iframe {
  display: block;
  width: 100%;
  max-width: 900px;
  height: 600px;
  margin: 0 auto;
  border: 1px solid var(--soft-rule);
  background: var(--media-bg);
}

/* Quotations and notes. */
.markdown-body blockquote {
  padding: 0.35rem 1.2rem;
  border-left: 3px solid var(--rule);
  color: var(--quote-text);
  background: var(--quote-bg);
}

.markdown-body blockquote > :last-child {
  margin-bottom: 0;
}

.markdown-body .footnotes {
  margin-top: 4.5rem;
  padding-top: 1.4rem;
  border-top: 1px solid var(--soft-rule);
  color: var(--footnote-text);
  font-size: 0.86rem;
  line-height: 1.55;
}

.markdown-body sup {
  font-size: 0.72em;
}

/* A little more air around the major sections without giant GitHub rules. */
.markdown-body hr {
  max-width: var(--reader-measure);
  height: 1px;
  margin: 3rem auto;
  border: 0;
  background: var(--soft-rule);
}

@media (max-width: 900px) {
  .markdown-body {
    padding: 2.5rem 3rem 4rem !important;
  }
}

@media (max-width: 700px) {
  html,
  body {
    background-color: var(--page-bg);
  }

  html[data-reader-theme="paper"],
  html[data-reader-theme="paper"] body {
    background-color: #f4efe4;
  }

  html[data-reader-theme="dark"],
  html[data-reader-theme="dark"] body {
    background-color: #20201f;
  }

  .markdown-body {
    max-width: 100% !important;
    padding: 1.8rem 1.25rem 3.5rem !important;
    box-shadow: none;
  }

  .markdown-body:not([data-reader-size]) {
    --reader-font-size: 17px;
  }

  .markdown-body > h1:first-of-type {
    font-size: 2.1rem;
    letter-spacing: 0.03em;
  }

  .book-title-block {
    margin-bottom: 3rem;
  }

  .reader-settings-wrap {
    top: 0.5rem;
    margin-top: -1.4rem;
    margin-bottom: 2.1rem;
  }

  .reader-settings-panel {
    width: min(330px, calc(100vw - 2rem));
  }

  .markdown-body h2 {
    margin-top: 3.4rem;
    font-size: 1.55rem;
  }

  .markdown-body h3 {
    margin-top: 2.8rem;
    font-size: 1.27rem;
  }

  .markdown-body figure iframe {
    height: 68vw;
    min-height: 340px;
  }
}

@media print {
  html,
  body {
    background: #ffffff !important;
  }

  .reader-settings-wrap {
    display: none !important;
  }

  .markdown-body {
    --page-bg: #ffffff;
    --text: #000000;
    --muted: #444444;
    --soft-rule: #cccccc;
    --quote-bg: #ffffff;
    --quote-text: #222222;
    --footnote-text: #222222;

    max-width: none !important;
    padding: 0 !important;
    background: #ffffff !important;
    color: #000000 !important;
    box-shadow: none;
  }

  .markdown-body a {
    color: inherit;
  }
}


/* Persistent table of contents.
   Wide desktop: fixed in the left charcoal gutter.
   Laptop/tablet: left-edge drawer.
   Phone: use the normal in-page Contents section. */
.reader-toc-shell {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
}

.reader-toc-panel,
.reader-toc-toggle,
.reader-toc-close {
  font-family: inherit;
}

.reader-toc-panel {
  position: fixed;
  z-index: 60;
  box-sizing: border-box;
  color: #f4efea;
  background: rgba(35, 34, 33, 0.97);
  border: 1px solid rgba(255, 255, 255, 0.12);
}

.reader-toc-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.75rem;
  margin-bottom: 0.7rem;
  padding-bottom: 0.65rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.16);
}

.reader-toc-title {
  font-size: 0.76rem;
  font-weight: 800;
  letter-spacing: 0.11em;
  text-transform: uppercase;
}

.reader-toc-close {
  display: none;
  width: 2rem;
  height: 2rem;
  padding: 0;
  border: 0;
  border-radius: 50%;
  background: transparent;
  color: #f4efea;
  font-size: 1.35rem;
  line-height: 1;
  cursor: pointer;
}

.reader-toc-close:hover,
.reader-toc-close:focus-visible {
  background: rgba(255, 255, 255, 0.10);
}

.reader-toc-nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

.reader-toc-nav > ul > li {
  margin: 0.2rem 0 0.55rem;
}

.reader-toc-nav ul ul {
  margin: 0.25rem 0 0.45rem;
  padding-left: 0.68rem;
  border-left: 1px solid rgba(255, 255, 255, 0.15);
}

.reader-toc-nav li {
  margin: 0.16rem 0;
}

.reader-toc-nav a {
  display: block;
  padding: 0.26rem 0.36rem;
  border-left: 3px solid transparent;
  border-radius: 0.25rem;
  color: #ded8d2;
  font-size: 0.78rem;
  line-height: 1.28;
  text-decoration: none;
  overflow-wrap: anywhere;
  transition: background-color 120ms ease, color 120ms ease, border-color 120ms ease;
}

.reader-toc-nav > ul > li > a {
  color: #ffffff;
  font-size: 0.81rem;
  font-weight: 700;
}

.reader-toc-nav a:hover,
.reader-toc-nav a:focus-visible {
  background: rgba(255, 255, 255, 0.08);
  color: #ffffff;
  outline: none;
}

.reader-toc-nav a.is-current {
  border-left-color: #cf7373;
  background: rgba(207, 115, 115, 0.16);
  color: #ffffff;
}

.reader-toc-nav a.is-current-parent {
  color: #ffffff;
}

.reader-toc-toggle {
  display: none;
  position: fixed;
  z-index: 59;
  align-items: center;
  gap: 0.42rem;
  padding: 0.58rem 0.72rem 0.58rem 0.62rem;
  border: 1px solid rgba(255, 255, 255, 0.16);
  border-left: 0;
  border-radius: 0 0.55rem 0.55rem 0;
  background: #2f2f2f;
  color: #ffffff;
  box-shadow: 0 3px 12px rgba(0, 0, 0, 0.18);
  font-size: 0.78rem;
  font-weight: 700;
  letter-spacing: 0.035em;
  cursor: pointer;
}

.reader-toc-toggle-icon {
  font-size: 1rem;
  line-height: 1;
}

.reader-toc-toggle:hover,
.reader-toc-toggle:focus-visible {
  background: #3a3938;
  outline: 2px solid var(--rule);
  outline-offset: 2px;
}

.reader-toc-scrim {
  display: none;
}

/* The in-page Contents is the single source used to populate the side TOC. */
.in-page-contents {
  max-width: var(--reader-measure);
  margin-left: auto;
  margin-right: auto;
}

.in-page-contents > ul {
  padding-left: 1.35rem;
  line-height: 1.52;
}

.in-page-contents > ul > li {
  margin: 0.45rem 0;
}

.in-page-contents > ul ul {
  margin-top: 0.3rem;
  margin-bottom: 0.55rem;
}

/* Tablet and desktop use the persistent/drawer navigation instead. */
@media (min-width: 701px) {
  .in-page-contents {
    display: none;
  }
}

/* Wide desktop: fit the navigation into the actual left gutter. */
@media (min-width: 1600px) {
  .reader-toc-panel {
    display: block;
    top: 1.1rem;
    left: 12px;
    width: min(240px, calc((100vw - 1200px) / 2 - 24px));
    min-width: 176px;
    max-height: calc(100vh - 2.2rem);
    padding: 0.85rem 0.7rem 1rem;
    overflow-y: auto;
    overscroll-behavior: contain;
    border-radius: 0.7rem;
    scrollbar-width: thin;
    scrollbar-color: rgba(255, 255, 255, 0.28) transparent;
  }

  .reader-toc-panel::-webkit-scrollbar {
    width: 7px;
  }

  .reader-toc-panel::-webkit-scrollbar-thumb {
    background: rgba(255, 255, 255, 0.25);
    border-radius: 999px;
  }
}

/* Laptop/tablet: collapse the TOC into a left-edge drawer. */
@media (min-width: 701px) and (max-width: 1599px) {
  .reader-toc-toggle {
    display: flex;
    top: 5.25rem;
    left: 0;
  }

  .reader-toc-panel {
    top: 0;
    left: 0;
    width: min(360px, 86vw);
    height: 100vh;
    padding: 1.15rem 1rem 1.4rem;
    overflow-y: auto;
    overscroll-behavior: contain;
    border-radius: 0 0.75rem 0.75rem 0;
    transform: translateX(-105%);
    transition: transform 180ms ease;
  }

  .reader-toc-close {
    display: inline-grid;
    place-items: center;
  }

  .reader-toc-scrim {
    position: fixed;
    inset: 0;
    z-index: 58;
    background: rgba(0, 0, 0, 0.35);
  }

  .reader-toc-shell.is-open .reader-toc-panel {
    transform: translateX(0);
    box-shadow: 10px 0 30px rgba(0, 0, 0, 0.28);
  }

  .reader-toc-shell.is-open .reader-toc-scrim {
    display: block;
  }

  .reader-toc-shell.is-open .reader-toc-toggle {
    visibility: hidden;
  }
}

/* Phones use the normal in-document Contents section. */
@media (max-width: 700px) {
  .reader-toc-shell {
    display: none !important;
  }
}

html[data-reader-theme="paper"] .reader-toc-panel,
html[data-reader-theme="paper"] .reader-toc-toggle {
  background: #37332f;
}

html[data-reader-theme="dark"] .reader-toc-panel,
html[data-reader-theme="dark"] .reader-toc-toggle {
  background: #151515;
}

@media print {
  .reader-toc-shell {
    display: none !important;
  }

  .in-page-contents {
    display: block !important;
  }
}

</style>

<div class="book-title-block">
  <p class="book-subtitle"><strong>Rediscovering a Lost Vernacular Landscape</strong></p>
  <p class="book-kicker"><em>An Open Educational Resource</em></p>
  <p class="book-author">Nathan Elliot Marvin</p>
</div>

<div class="reader-settings-wrap">
  <details class="reader-settings" id="reader-settings">
    <summary><span class="reader-settings-aa" aria-hidden="true">Aa</span><span>Reading settings</span></summary>
    <div class="reader-settings-panel" role="group" aria-label="Reading settings">
      <fieldset>
        <legend>Text size</legend>
        <div class="reader-options">
          <button type="button" class="reader-setting-button" data-reader-setting="size" data-reader-value="small" aria-pressed="false" aria-label="Smaller text">A−</button>
          <button type="button" class="reader-setting-button" data-reader-setting="size" data-reader-value="default" aria-pressed="true" aria-label="Default text size">A</button>
          <button type="button" class="reader-setting-button" data-reader-setting="size" data-reader-value="large" aria-pressed="false" aria-label="Larger text">A+</button>
          <button type="button" class="reader-setting-button" data-reader-setting="size" data-reader-value="xlarge" aria-pressed="false" aria-label="Extra-large text">A++</button>
        </div>
      </fieldset>

      <fieldset>
        <legend>Text width</legend>
        <div class="reader-options">
          <button type="button" class="reader-setting-button" data-reader-setting="width" data-reader-value="narrow" aria-pressed="false">Narrow</button>
          <button type="button" class="reader-setting-button" data-reader-setting="width" data-reader-value="default" aria-pressed="true">Default</button>
          <button type="button" class="reader-setting-button" data-reader-setting="width" data-reader-value="wide" aria-pressed="false">Wide</button>
        </div>
      </fieldset>

      <fieldset>
        <legend>Line spacing</legend>
        <div class="reader-options">
          <button type="button" class="reader-setting-button" data-reader-setting="spacing" data-reader-value="compact" aria-pressed="false">Compact</button>
          <button type="button" class="reader-setting-button" data-reader-setting="spacing" data-reader-value="default" aria-pressed="true">Default</button>
          <button type="button" class="reader-setting-button" data-reader-setting="spacing" data-reader-value="spacious" aria-pressed="false">Spacious</button>
        </div>
      </fieldset>

      <fieldset>
        <legend>Typeface</legend>
        <div class="reader-options">
          <button type="button" class="reader-setting-button" data-reader-setting="font" data-reader-value="serif" aria-pressed="true">Serif</button>
          <button type="button" class="reader-setting-button" data-reader-setting="font" data-reader-value="sans" aria-pressed="false">Sans serif</button>
        </div>
      </fieldset>

      <fieldset>
        <legend>Theme</legend>
        <div class="reader-options">
          <button type="button" class="reader-setting-button" data-reader-setting="theme" data-reader-value="light" aria-pressed="true">Light</button>
          <button type="button" class="reader-setting-button" data-reader-setting="theme" data-reader-value="paper" aria-pressed="false">Paper</button>
          <button type="button" class="reader-setting-button" data-reader-setting="theme" data-reader-value="dark" aria-pressed="false">Dark</button>
        </div>
      </fieldset>

      <div class="reader-settings-footer">
        <p class="reader-settings-note">Your choices are saved on this device.</p>
        <button type="button" class="reader-settings-reset" id="reader-settings-reset">Reset</button>
      </div>
      <p class="sr-only" id="reader-settings-status" aria-live="polite"></p>
    </div>
  </details>
</div>


<div class="reader-toc-shell" id="reader-toc-shell">
  <button type="button" class="reader-toc-toggle" id="reader-toc-toggle" aria-controls="reader-toc-panel" aria-expanded="false">
    <span class="reader-toc-toggle-icon" aria-hidden="true">☰</span>
    <span>Contents</span>
  </button>
  <aside class="reader-toc-panel" id="reader-toc-panel" aria-label="Contents">
    <div class="reader-toc-header">
      <span class="reader-toc-title">Contents</span>
      <button type="button" class="reader-toc-close" id="reader-toc-close" aria-label="Close contents">×</button>
    </div>
    <nav class="reader-toc-nav" id="reader-toc-nav" aria-label="Table of contents"></nav>
  </aside>
  <div class="reader-toc-scrim" id="reader-toc-scrim" aria-hidden="true"></div>
</div>

<section class="in-page-contents" id="contents" aria-labelledby="contents-heading">
  <h2 id="contents-heading">Contents</h2>
  <ul>
    <li><a href="#creole-arkansas">Creole Arkansas</a></li>
    <li><a href="#the-creole-corridor">The Creole Corridor</a></li>
    <li><a href="#landscapes-of-erasure">Landscapes of Erasure</a></li>
    <li><a href="#breaking-down-myths">Breaking Down Myths</a></li>
    <li><a href="#la-petite-roche">"La Petite Roche"</a></li>
    <li><a href="#looking-for-petit-jean">Looking for Petit Jean</a></li>
    <li><a href="#survival-strategies">Survival Strategies</a></li>
    <li><a href="#references">References</a></li>
  </ul>
</section>

<a id="creole-arkansas"></a>
## Creole Arkansas

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

[↑ Back to Contents](#contents)


<a id="the-creole-corridor"></a>
## The Creole Corridor

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

[↑ Back to Contents](#contents)


<a id="landscapes-of-erasure"></a>
## Landscapes of Erasure

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

[↑ Back to Contents](#contents)


<a id="breaking-down-myths"></a>
## Breaking Down Myths

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

[↑ Back to Contents](#contents)


<a id="la-petite-roche"></a>
## "La Petite Roche"

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

[↑ Back to Contents](#contents)


<a id="looking-for-petit-jean"></a>
## Looking for Petit Jean

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

[↑ Back to Contents](#contents)


<a id="survival-strategies"></a>
## Survival Strategies

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

[↑ Back to Contents](#contents)


<a id="references"></a>
## References

<!-- StoryMap text, images, maps, captions, and notes will be inserted here. -->

<script>
(function () {
  var reader = document.querySelector('.markdown-body');
  var settingsBox = document.getElementById('reader-settings');
  var resetButton = document.getElementById('reader-settings-reset');
  var status = document.getElementById('reader-settings-status');

  if (!reader || !settingsBox) return;

  var storageKey = 'freedomDeferredReaderSettings';
  var defaults = {
    size: 'default',
    width: 'default',
    spacing: 'default',
    font: 'serif',
    theme: 'light'
  };

  var attributes = {
    size: 'data-reader-size',
    width: 'data-reader-width',
    spacing: 'data-reader-spacing',
    font: 'data-reader-font',
    theme: 'data-reader-theme'
  };

  function loadSettings() {
    try {
      var saved = JSON.parse(localStorage.getItem(storageKey));
      if (!saved || typeof saved !== 'object') return Object.assign({}, defaults);
      return Object.assign({}, defaults, saved);
    } catch (error) {
      return Object.assign({}, defaults);
    }
  }

  function saveSettings(settings) {
    try {
      localStorage.setItem(storageKey, JSON.stringify(settings));
    } catch (error) {
      /* The reader still works if local storage is unavailable. */
    }
  }

  function setAttributeOrDefault(setting, value) {
    var attribute = attributes[setting];
    var isDefault =
      (setting === 'size' && value === 'default') ||
      (setting === 'width' && value === 'default') ||
      (setting === 'spacing' && value === 'default') ||
      (setting === 'font' && value === 'serif') ||
      (setting === 'theme' && value === 'light');

    if (isDefault) {
      reader.removeAttribute(attribute);
    } else {
      reader.setAttribute(attribute, value);
    }
  }

  function updateButtons(settings) {
    var buttons = settingsBox.querySelectorAll('[data-reader-setting]');
    buttons.forEach(function (button) {
      var setting = button.getAttribute('data-reader-setting');
      var value = button.getAttribute('data-reader-value');
      button.setAttribute('aria-pressed', String(settings[setting] === value));
    });
  }

  function applySettings(settings, announce) {
    Object.keys(defaults).forEach(function (setting) {
      setAttributeOrDefault(setting, settings[setting]);
    });

    if (settings.theme === 'light') {
      document.documentElement.removeAttribute('data-reader-theme');
    } else {
      document.documentElement.setAttribute('data-reader-theme', settings.theme);
    }

    updateButtons(settings);

    if (announce && status) {
      status.textContent = 'Reading settings updated.';
    }
  }

  var current = loadSettings();
  applySettings(current, false);

  settingsBox.addEventListener('click', function (event) {
    var button = event.target.closest('[data-reader-setting]');
    if (!button) return;

    var setting = button.getAttribute('data-reader-setting');
    var value = button.getAttribute('data-reader-value');
    current[setting] = value;
    saveSettings(current);
    applySettings(current, true);
  });

  if (resetButton) {
    resetButton.addEventListener('click', function () {
      current = Object.assign({}, defaults);
      try {
        localStorage.removeItem(storageKey);
      } catch (error) {
        /* Ignore storage errors. */
      }
      applySettings(current, false);
      if (status) status.textContent = 'Reading settings reset to defaults.';
    });
  }

  document.addEventListener('keydown', function (event) {
    if (event.key === 'Escape' && settingsBox.open) {
      settingsBox.open = false;
      settingsBox.querySelector('summary').focus();
    }
  });

  document.addEventListener('click', function (event) {
    if (settingsBox.open && !settingsBox.contains(event.target)) {
      settingsBox.open = false;
    }
  });
})();
</script>

<script>
(function () {
  var shell = document.getElementById('reader-toc-shell');
  var panel = document.getElementById('reader-toc-panel');
  var nav = document.getElementById('reader-toc-nav');
  var toggle = document.getElementById('reader-toc-toggle');
  var closeButton = document.getElementById('reader-toc-close');
  var scrim = document.getElementById('reader-toc-scrim');
  var sourceContents = document.querySelector('.in-page-contents');
  var sourceList = sourceContents ? sourceContents.querySelector(':scope > ul') : null;

  if (!shell || !panel || !nav || !toggle || !sourceContents || !sourceList) {
    if (shell) shell.style.display = 'none';
    return;
  }

  /* Clone from an explicit Contents container rather than relying on
     Jekyll's rendered sibling structure. */
  nav.replaceChildren(sourceList.cloneNode(true));

  function isWideDesktop() {
    return window.innerWidth >= 1600;
  }

  function openDrawer() {
    if (isWideDesktop()) return;
    shell.classList.add('is-open');
    toggle.setAttribute('aria-expanded', 'true');
    panel.setAttribute('tabindex', '-1');
    panel.focus();
  }

  function closeDrawer(returnFocus) {
    shell.classList.remove('is-open');
    toggle.setAttribute('aria-expanded', 'false');
    if (returnFocus && !isWideDesktop()) toggle.focus();
  }

  toggle.addEventListener('click', function () {
    if (shell.classList.contains('is-open')) {
      closeDrawer(false);
    } else {
      openDrawer();
    }
  });

  if (closeButton) {
    closeButton.addEventListener('click', function () {
      closeDrawer(true);
    });
  }

  if (scrim) {
    scrim.addEventListener('click', function () {
      closeDrawer(true);
    });
  }

  document.addEventListener('keydown', function (event) {
    if (event.key === 'Escape' && shell.classList.contains('is-open')) {
      closeDrawer(true);
    }
  });

  nav.addEventListener('click', function (event) {
    var link = event.target.closest('a[href^="#"]');
    if (!link) return;
    if (!isWideDesktop()) closeDrawer(false);
  });

  window.addEventListener('resize', function () {
    if (isWideDesktop()) closeDrawer(false);
  });

  /* On tablet/desktop, "Back to Contents" opens or focuses the persistent TOC
     instead of jumping to a hidden in-page Contents section. */
  document.addEventListener('click', function (event) {
    var link = event.target.closest('a[href="#contents"]');
    if (!link || window.innerWidth <= 700) return;

    event.preventDefault();

    if (isWideDesktop()) {
      panel.scrollTo({ top: 0, behavior: 'smooth' });
      var firstLink = nav.querySelector('a');
      if (firstLink) firstLink.focus({ preventScroll: true });
    } else {
      openDrawer();
    }
  });

  /* Highlight the section/source nearest the top of the reading pane. */
  var links = Array.prototype.slice.call(nav.querySelectorAll('a[href^="#"]'));
  var ticking = false;

  function updateCurrentLink() {
    ticking = false;
    var current = null;
    var threshold = 150;

    links.forEach(function (link) {
      var hash = link.getAttribute('href');
      if (!hash || hash.length < 2) return;

      var id;
      try {
        id = decodeURIComponent(hash.slice(1));
      } catch (error) {
        id = hash.slice(1);
      }

      var target = document.getElementById(id);
      if (target && target.getBoundingClientRect().top <= threshold) {
        current = link;
      }
    });

    links.forEach(function (link) {
      link.classList.remove('is-current', 'is-current-parent');
      link.removeAttribute('aria-current');
    });

    if (!current) return;

    current.classList.add('is-current');
    current.setAttribute('aria-current', 'location');

    var parentList = current.closest('ul');
    if (parentList && parentList.parentElement && parentList.parentElement.tagName === 'LI') {
      var parentLink = parentList.parentElement.querySelector(':scope > a');
      if (parentLink) parentLink.classList.add('is-current-parent');
    }

    if (isWideDesktop()) {
      var panelRect = panel.getBoundingClientRect();
      var currentRect = current.getBoundingClientRect();

      if (currentRect.top < panelRect.top + 52 || currentRect.bottom > panelRect.bottom - 18) {
        current.scrollIntoView({ block: 'nearest', behavior: 'smooth' });
      }
    }
  }

  function requestCurrentUpdate() {
    if (ticking) return;
    ticking = true;
    window.requestAnimationFrame(updateCurrentLink);
  }

  window.addEventListener('scroll', requestCurrentUpdate, { passive: true });
  window.addEventListener('resize', requestCurrentUpdate);
  window.addEventListener('load', requestCurrentUpdate);
  requestCurrentUpdate();
})();
</script>
