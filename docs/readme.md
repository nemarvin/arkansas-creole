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
  background-color: var(--control-bg);
  color: var(--text);
  opacity: 1;
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

<style>
.markdown-body > figure.interactive-map {
  max-width: 1120px;
}

.markdown-body > figure.interactive-map iframe {
  width: 100%;
  max-width: 1120px;
  height: 690px;
  border: 1px solid var(--soft-rule);
  border-radius: 2px;
}

.markdown-body .timeline-entry {
  max-width: var(--reader-measure);
  margin: 1.25rem auto;
  padding: 0.15rem 0 0.15rem 1rem;
  border-left: 2px solid var(--soft-rule);
}

.markdown-body .timeline-year {
  margin: 0 0 0.3rem;
  color: var(--rule);
  font-weight: 700;
}

.markdown-body .media-note {
  max-width: var(--reader-measure);
  margin: 1rem auto;
  color: var(--muted);
  font-size: 0.86rem;
  font-style: italic;
}

@media (max-width: 700px) {
  .markdown-body > figure.interactive-map iframe {
    height: 560px;
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
    <li><a href="#creole-arkansas">Creole Arkansas</a>
      <ul>
      </ul>
    </li>
    <li><a href="#the-creole-corridor">The Creole Corridor</a>
      <ul>
        <li><a href="#linchpin-of-la-louisiane">Linchpin of <em>La Louisiane</em></a></li>
      </ul>
    </li>
    <li><a href="#landscapes-of-erasure">Landscapes of Erasure</a>
      <ul>
        <li><a href="#a-french-river-world">A "French River World"</a></li>
      </ul>
    </li>
    <li><a href="#breaking-down-myths">Breaking Down Myths</a>
      <ul>
        <li><a href="#middle-ground-native-ground">Middle Ground, Native Ground</a></li>
      </ul>
    </li>
    <li><a href="#la-petite-roche">"La Petite Roche"</a>
      <ul>
        <li><a href="#le-petit-rocher">Le Petit Rocher</a></li>
        <li><a href="#french-speaking-settlers-in-little-rock">French-Speaking Settlers in Little Rock</a></li>
        <li><a href="#creole-land-claims-and-the-1818-quapaw-treaty-line">Creole Land Claims and the 1818 Quapaw Treaty Line</a></li>
        <li><a href="#haitian-revolution-emigr-s">Haitian Revolution Emigrés</a></li>
      </ul>
    </li>
    <li><a href="#looking-for-petit-jean">Looking for Petit Jean</a>
      <ul>
        <li><a href="#a-legendary-brand">A Legendary Brand</a></li>
        <li><a href="#the-real-petit-jean">The "Real" Petit Jean?</a></li>
        <li><a href="#contested-sovereignty">Contested Sovereignty</a></li>
        <li><a href="#the-documents">The Documents</a></li>
        <li><a href="#roma-in-france-and-its-empire">Roma in France and its Empire</a></li>
        <li><a href="#romani-diaspora-in-french-louisiana">Romani Diaspora in French Louisiana</a></li>
        <li><a href="#racial-liminality">"Racial Liminality"</a></li>
        <li><a href="#burying-petit-jean">Burying Petit Jean</a></li>
        <li><a href="#evolution-of-a-legend">Evolution of a Legend</a></li>
      </ul>
    </li>
    <li><a href="#survival-strategies">Mapping Survival Strategies</a>
      <ul>
        <li><a href="#mapping-survival-strategies">Spanish Land Grants</a></li>
        <li><a href="#lines-of-dispossession-us-quapaw-treaties">Lines of Quapaw Dispossession</a></li>
        <li><a href="#a-creole-carve-out">A Mixed-Ancestry Carve-Out</a></li>
        <li><a href="#joining-indian-removal-arkansass-m-tis-creoles-and-the-treaty-of-1833">Joining Indian Removal</a></li>
        <li><a href="#the-villemonts-of-chicot-county">The Villemonts of Chicot County</a></li>
        <li><a href="#northeast-arkansas">Northeast Arkansas</a></li>
        <li><a href="#st-marys-church-anchor-of-a-community">St. Mary’s Church: Anchor of a Community</a></li>
        <li><a href="#baptisms-and-burials">Baptisms and Burials</a></li>
      </ul>
    </li>
    <li><a href="#references">References</a>
      <ul>
        <li><a href="#secondary-sources">Secondary Sources</a></li>
        <li><a href="#published-primary-sources">Published Primary Sources</a></li>
        <li><a href="#archival-collections">Archival Collections</a></li>
        <li><a href="#acknowledgements">Acknowledgements</a></li>
        <li><a href="#community-sourcing">Community Sourcing</a></li>
        <li><a href="#process-and-ethics">Process and Ethics</a></li>
      </ul>
    </li>
  </ul>
</section>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/5LM96J-UGeR_DhHBhw0z3.jpeg" alt=" A lone tree stands on a cliff overlooking a vast valley on the south-facing side of Mount Nebo in Mount Nebo State Park, Dardanelle, Arkansas." loading="lazy" decoding="async">
  <figcaption>View from Mount Nebo State Park, Arkansas. Image from the original <em>Arkansas Créole</em> StoryMap.</figcaption>
</figure>

<blockquote><em>"We live among countless landscapes of memory in this country. They convey both remembrance and omission[.] … Layers upon layers of names and meanings lie beneath the official surface."</em></blockquote>

— Lauret Savoy, <em>Trace</em>

<a id="creole-arkansas"></a>
## Creole Arkansas

French roots run deep in Arkansas. It was here, near the original site of Arkansas Post, in the late seventeenth century, that Sieur de la Salle envisioned the heart of France’s North American empire. What emerged—<em>La Louisiane</em>—did indeed include Arkansas: a vast arc of forts and settlements linking the Gulf of Mexico to the Great Lakes, and beyond to the North Atlantic and France itself. French officials hoped this network of outposts would serve as a bulwark against British expansion to the east and Spanish claims to the south and west.

We think we know the rest of the story... French ambitions in North America came to a halt with their defeat by Great Britain in the Seven Years’ War. Although the Spanish takeover of <em>La Louisiane</em> preserved many cultural, religious, and legal norms, most remaining Francophone communities faded away after the 1803 Louisiana Purchase opened the door to rapid Anglo-American settlement.

In fact, Creole culture in Arkansas persisted. French-speaking hunters and settlers—many of mixed European and Indigenous ancestry—as well as enslaved and formerly enslaved people of African descent, continued to live and work in the region. New French speakers arrived as well, albeit in smaller numbers, even after Arkansas was acquired by the United States and organized as a territory in 1819.

So why do we know so little about these Creoles of Arkansas and the world they made? This project aims to shed light on the forces behind that erasure—and to help recover a long-obscured and often misunderstood chapter of our history—by tracing their stories across the state’s geography, through place names both preserved and lost. It also seeks to make the myth-busting work of scholars more accessible, highlighting new archival discoveries and fresh interpretations of familiar sources. By recovering these stories, we hope to offer a fuller, more accurate—and thus more inclusive—vision of early Arkansas, helping foster a deeper sense of place for all of us who call it home today.

<blockquote><em>"</em><em><strong>Creole</strong></em><em> (En; adj); </em><em><strong>Créole</strong></em><em> (Fr n, m/f; adj); </em><em><strong>Kreyol, Kreol</strong></em><em> (FC n, m/f; adj); </em><em><strong>Criollo</strong></em><em> (Sp n, m/f; adj); </em><em><strong>Crioulo</strong></em><em> (P n, m/f; adj)... From L[atin] adj. 'Something bred or raised.' </em></blockquote>

—<em> A Creole Lexicon </em>(LSU Press, 2004)

What is a "Creole"? What is an "Arkansas Creole"? In their historical dictionary of Louisiana vocabulary, <em>A Creole Lexicon</em>, scholars Glenn R. Edwards, Jay Dearborn Edwards, and Nicolas Kariouk Pecquet du Bellay de Verton show how the meaning of the term "Creole" evolved over time. In the 15th through 18th centuries, the term generally referred to people born in European colonies—places like Louisiana, Brazil, the West Indies, or France's Indian Ocean colonies—who descended from European or African settlers. In Upper Louisiana, the term was often used more narrowly to describe white descendants of French colonists, a meaning that lingered well into the twentieth century—even as far north as Canada, where it still described residents of the Great Lakes region.

But "Creole" could also carry broader cultural meanings. Over time, it came to include descendants of those early Creoles as well as people who had assimilated into Creole communities. In Louisiana and its neighboring regions, including what is now Arkansas, that might mean someone of French, Spanish, African, or Indigenous ancestry—or any mix thereof—so long as they were a part of the region’s French-speaking world.

This project uses "Arkansas Creoles" as a category of analysis—in other words, it wasn’t necessarily a term the community used to describe itself. Many would likely have identified simply as French. When they spoke of their home, they often used a broader term drawn from the French name for the river—and for the Indigenous nation who lived at its confluence with the Mississippi: the Arkansas country (<em>pays aux Arcs</em>) (Schroeder 2007, 168). Anglo-American settlers, and before them Spanish authorities, often used some version of the word "Creole"—or simply "French"—to describe these individuals and communities. In this context, Arkansas Creoles refers to people who were born in Arkansas—or who lived, labored, or settled here—and who were primarily French-speaking or part of the region’s French-speaking communities in the eighteenth and nineteenth centuries.

French-speaking settlers and their descendants in the region forged a lasting partnership with the Quapaw (<em>Okáxpa</em>) Nation, whom the French called <em>Arkansas</em>, whose sovereignty they recognized, and whose support they relied on for both prosperity and survival—especially in the early years of settlement. Most Arkansas Creoles were of European background, but many also had Indigenous members in their family trees. A smaller number were of African descent.

Mixed ancestry extended into the highest ranks of colonial Arkansas society. The wife of Arkansas Post commandant Jean-François Tisserant de Montcharvaux, a nobleman from France, was the granddaughter of Marie Rouensa-8canic8e, the daughter of a Kaskaskia chief who converted to Catholicism (Ekberg and Pregaldin 2007, 216).

<figure>
  <img src="YOUR-IMAGE-URL" alt="View of the Arkansas River from Big Rock toward Pinnacle Mountain" loading="lazy" decoding="async">
  <figcaption><strong>image:</strong> View of the Arkansas River, looking from Big Rock toward Pinnacle Mountain (once called <em>la mamelle</em> in French)—two landmarks of river navigation well known to Arkansas Creoles; Big Rock, the first major outcrop on the river, lies 121 miles above its confluence with the Mississippi, and in 1722 French explorer Jean-Baptiste Bénard de La Harpe ascended the bluff, naming it <em>le rocher français</em> (“French Rock”) in honor of the king of France (Buck 2024); to the Quapaw (Ogahpah), the river was <em>ni zhi-te</em> (“red river”), a name echoed nearly a century later, in 1827, by Baptiste Imbeau—an Arkansas Creole of French and Lipan Apache ancestry who presented himself, and was recognized by both U.S. and Quapaw officials, as a “French Quapaw”; George Izard, second territorial governor of Arkansas, conducted his interviews on Quapaw language and customs entirely in French and noted in his report to the American Philosophical Society that local interpreters were “exclusively French Creoles or half-breeds” (Arnold 2016; Bandy 2020; Izard 1827a).</figcaption>
</figure>

[↑ Back to Contents](#contents)

<a id="the-creole-corridor"></a>
## The Creole Corridor

Arkansas was an integral part of what historian Jay Gitlin has called the “Creole Corridor”—a constellation of interconnected French-speaking posts and settlements stretching from the St. Lawrence Valley through the Great Lakes and down the Mississippi River (Gitlin 2010). Mobility was key to the making and maintaining of this "French river world" in the heart of North America (Teasdale and Villerbu 2015; Wegmann and Englebert 2020).

<a id="linchpin-of-la-louisiane"></a>
### Linchpin of <em>La Louisiane</em>

Although there were perhaps never more than a thousand subjects of the Spanish empire in what is now the state of Arkansas prior to U.S. annexation, many more moved through the region, traveling along the network of settlements that historians have called the “Creole Corridor.” This corridor stretched from New Orleans to the Canadian Maritimes—and extended outward in all directions.

Although not as densely settled as the Illinois Country establishments to the north (Ekberg, Nasatir, and Schram 2014; White 2012; Heerman 2018; Gitlin, Morrissey, and Kastor 2021)—which extended into the Ozark Mountains (Schroeder 2016)—or the plantation zones of the Cane and Red Rivers to the south (Burton and Smith 2008; Mills et al. 2013), Arkansas served as a crucial linchpin connecting these French-speaking regions. For many years, the Arkansas Post was the only major settlement between Upper Louisiana (<em>la Haute-Louisiane</em>) and Lower Louisiana (<em>la Basse-Louisiane</em>) (Arnold 2017).

<figure class="interactive-map">
  <iframe src="maps/creole-corridor.html"
          title="Interactive map of the Creole Corridor"
          loading="lazy"
          allowfullscreen></iframe>
  <figcaption>Interactive map of settlements along the Creole Corridor. Click a point to open the details panel.</figcaption>
</figure>

[↑ Back to Contents](#contents)

<a id="landscapes-of-erasure"></a>
## Landscapes of Erasure

In his pathbreaking work on early Arkansas Post, historian Morris Arnold describes the “cosmopolitan character” of the society that developed there, where military officers and other notables interacted daily with settlers, soldiers, farmers, hunters, and <em>voyageurs</em> (boatmen)—Europeans and European Americans alongside “Indians, métis, and African slaves.” This diverse social world, he notes, endured “for upwards of 200 years, until the flood of American immigration, and a civil war, finally submerged it and all but entirely erased its memory” (Arnold 2015a, 15). This project seeks to reverse that effect by highlighting placenames—some still in use, others long forgotten—that illuminate the Creole experience in early Arkansas, in all its cultural richness and complexity.

It also aims to understand the "erasure" itself. How did this process unfold—and why? In many ways, it begins with the history books. In the nineteenth and early twentieth centuries, those responsible for writing and disseminating “official” narratives of Arkansas often elided or romanticized its “French period.” By the late nineteenth century, textbooks written for English-language schools in Arkansas portrayed the French presence as a brief and inconsequential chapter. These accounts leaned heavily on stereotypes, depicting French settlers as ignorant and living in inappropriately close proximity to Indigenous people—intermarriage was frequently cited—who were themselves cast as obstacles to the inevitable westward advance of the American nation (Shinn 1898). This framing made the “French” both an object of derision and, somewhat paradoxically, unwitting allies in the project of American expansion: one textbook even claimed that the amicable relationships between “Creoles” and Native communities had smoothed the path for Anglo-American settlement, in contrast to the violent resistance encountered elsewhere (Reynolds 1905).

These narratives—and the assumptions that underpinned them—reflected broader trends in Anglo-American historiography. They align closely, for example, with the interpretations advanced by George Bancroft and Francis Parkman, two towering figures in what is often described as the “Romantic nationalist” school of history—a style of writing that actively served the project of nation-building. Shaped by their Puritan New England backgrounds and educations, both Bancroft and Parkman promoted a vision of American virtue and destiny, casting the United States as a continental power fated to expand from east to west (Usner 2005).

By characterizing French colonies as quasi-medieval, priest-ridden outposts lacking in self-sustaining vitality, these historians reinforced the idea that Anglo-American civilization had a superior claim to North America. Their interpretations helped cast the French as insignificant players – courageous perhaps, but ultimately losers in the grand saga, and chiefly important for how they set the stage for British-American triumph. This approach both reflected and informed broader trends in American education.

Yet as much as these textbooks portrayed the French presence as a brief interlude or a stepping stone to U.S. expansion, many still noted that Creole descendants continued to live throughout the state, especially in the area around Pine Bluff. A few even acknowledged their most enduring legacy: the names etched into Arkansas’s geography. Writing in 1908, John Michael Lucey—an Irish-American Confederate veteran turned Catholic priest serving in Pine Bluff—echoed what many locals already knew: that French-speaking families had not disappeared with U.S. annexation but had remained for generations. In his historical study, The Catholic Church in Arkansas, he connected these families to the state's geography:

<blockquote><em>"Until about fifty years ago the influence of French immigrants and their mode of life was very strong... Many of our mountains and streams and some of our cities and their streets bear French names or Gallicised Indian names.”  </em></blockquote>

—John Michael Lucey, 1908

<a id="a-french-river-world"></a>
### A "French River World"

What remains today of the landscapes of Creole Arkansas? Over time, the corruption and Anglicization of French place names contributed to the gradual erasure of this legacy from public memory. To find traces of it, one must look to the waterways that once sustained it—the rivers, bayous, and streams that linked hunting grounds to trading posts, and the hills and ridges that served as navigational markers. A map of surviving place names clustered around the confluences of smaller waterways with major rivers reveals a once-interconnected riverine world, centered primarily along three arteries feeding into the Mississippi: the Arkansas, White, and Ouachita Rivers. For many settlers and hunters in these communities during the eighteenth and nineteenth centuries, life was lived on the water. As a result, the names they left behind tend to mark bayous, landings, marshes, riverside campsites, and other key sites of movement and subsistence. These families branched out along the web of swamps and tributaries that connected the region’s great rivers—a watery network where Creole presence left its most enduring imprint.

In some cases, the spelling and pronunciation of place names have changed so significantly that their original meanings—often tied to how a feature of the landscape was used or recognized for navigation—have been lost. For instance, Mount Magazine (originally <em>magasin</em>) likely referred to the mountain’s barn-like shape, serving as a visual marker for travelers along the Arkansas River. “Smackover” may be a corruption of the French <em>chemin couvert</em>, meaning “covered way”—not in the sense of being hidden, but rather shaded or overhung by a canopy of trees along the creek from which the town took its name.

And would you guess that Glazypool, Cassa Massa, Grandee Lake, and Darysaw are named not just for landmarks, but for actual individuals and families? Who were the people behind these place names? Click the points on the map to reveal more about their stories.

<figure class="interactive-map">
  <iframe src="maps/arkansas-creole-place-names.html"
          title="Interactive map of Arkansas Créole place names"
          loading="lazy"
          allowfullscreen></iframe>
  <figcaption>Interactive map of Arkansas Créole place names. Search, filter, or click a point to explore historical names, notes, images, and sources.</figcaption>
</figure>

[↑ Back to Contents](#contents)

<a id="breaking-down-myths"></a>
## Breaking Down Myths

Myths about the Arkansas region and its French-speaking heritage abound. This project builds on the pioneering work of scholars such as Morris Arnold, Andrew Beaupré, Kathleen DuVal, and Sonia Toudji to foreground new research and dispel enduring misconceptions about early Arkansas history.

The first myth—and perhaps the most enduring—is the myth of European dominance in this region, a narrative perpetuated by widely circulated historical maps. Produced in the metropoles of Europe—whether Spanish, British, or French—these maps were often tools of imperial propaganda, designed to project the illusion of territorial control in competition with rival European and Native powers. In many cases, they were deliberately crafted to undermine or erase Indigenous sovereignty claims. At the very least, they obscured the foundational role of Native knowledge in shaping the very geographical information that underpinned state-sponsored cartography.

And yet, American and world history textbooks continue to rely heavily on schematic, color-shaded maps derived from these originals. These visuals routinely portray vast expanses of territory as being firmly under European control, while the land claims and political realities of Native nations are rarely included within the same visual frame—if they are acknowledged at all. In truth, as scholars have shown, the reality was often the inverse of what such maps suggest: Indigenous peoples exercised significant and sustained influence throughout the North American interior and West well into the eighteenth century (Evans 2024).

Outsiders in the late eighteenth and early nineteenth centuries often portrayed Arkansas Creoles as carefree people, living in harmonious proximity to Indigenous nations and favoring the adventurous lives of <em>voyageurs</em> over more settled pursuits. In reality, the Creole world in Arkansas was far more complex. It centered on Arkansas Post and its surrounding farmsteads, where residents engaged in a mix of agricultural and commercial enterprises, in addition to hunting (Arnold 2017).

Moreover, like other former French territories in North America, Arkansas has often been portrayed as a romantic, bucolic, and benign place prior to American expansion. In reality, it was shaped from the outset by violence and coercion. The first settlers were not “colonists” in the conventional sense, but men and women with little or no control over their destinies. They included soldiers, indentured servants, and deportees from France expelled to the penal colony of Louisiana, as well as enslaved Africans who formed the backbone of the colony’s labor force (Hall 1995; Dejean 2022).

The enslavement and forced migration of <em>both</em> Africans and Indigenous North Americans were historical processes that shaped virtually every European-colonial space in the Americas—including Arkansas. Indeed, slavery was a defining feature of Arkansas society before the arrival of Europeans and remained central until the end of the U.S. Civil War. In the 1790s, Francophone Arkansas saw a population increase driven by French-speaking settlers from the Illinois Country, who crossed the Mississippi River into Spanish-held territory precisely because they knew slavery would remain legal and protected under Spanish rule (Arnold 2017b).

Finally, another myth: France is often portrayed as having had a less violent impact on Indigenous nations in North America than its European rivals. In reality, French colonialism brought sweeping disruption to the region. Indigenous communities endured devastating population losses from diseases to which they had no immunity, cultural dislocation, and military campaigns that could be brutal. In some cases, such as French campaigns against the Fox, colonial violence has been likened to genocide (Havard and Vidal 2008). While France did not initially pose a territorial threat on the same scale as later Anglo-American expansion, its presence nonetheless reshaped Indigenous communities in lasting ways.

In other words, Creole Arkansas—and the broader Creole Corridor of which it was a part—was far from the tranquil, idyllic landscape evoked by the romantic river scenes of George Caleb Bingham. It was a world forged in violence from its very beginnings.

<a id="middle-ground-native-ground"></a>
### Middle Ground, Native Ground

<em>Métissage</em>—a French term referring to unions between European men and Indigenous women—was a pervasive feature of the Creole Corridor, and especially of early Arkansas. This pattern has often been cited as evidence of supposedly more liberal or inclusive attitudes toward Native peoples among French speakers, especially in contrast to their Anglophone neighbors. But such interpretations risk romanticizing these relationships, suggesting they were always voluntary or mutually beneficial. In reality, here as in other parts of the Creole Corridor, many of these unions involved captive women—marched east from their homelands, reduced to slavery, and sold into French colonial households (Arnold 2016; Marrero 2020). As early as the early eighteenth century, the trafficking of enslaved Indigenous captives had become central to French diplomacy with allied Native nations. Women and children made up the majority of those enslaved and sold to the French (Rushforth 2012).

While intermarriage or cohabitation between European—or European-descended—men and Native women was indeed widespread, this did not mean that French-speaking societies were fully integrated with those of the Quapaw in the Arkansas River Valley or the Osage to the north. The relationship between the French and the Quapaw, for example, was marked by reciprocity and peaceful coexistence between distinct nations—but not by full social or political integration. Throughout the eighteenth century, both the Quapaw and the Osage maintained the upper hand in diplomatic and trade relations with the French and, later, Spanish regimes (DuVal 2007; Toudji 2011a).

Evidence of this dynamic abounds in both the documentary and visual record. One of the earliest surviving representations of Arkansas Post—the oldest French settlement in what is now Arkansas—is not European in origin, but Quapaw. The “Three Villages Robe,” created in the mid-eighteenth century, centers a Quapaw military victory over their enemies (likely the Chickasaw). In one corner, however, the robe also depicts Arkansas Post: vertical wooden-post houses built in the French style, complete with <em>bousillage</em>, a hallmark of vernacular architecture in Upper Louisiana. French men are shown smoking tobacco and wearing <em>capots</em>, the distinctive hooded garments of the era. French soldiers stationed in Louisiana and at posts like Arkansas often wore the capot instead of standard regimental uniforms. Although not officially part of their issued dress, the capot was sometimes shipped from France or sourced locally. Soldiers adopted it because it was practical, well-suited to the climate, and functional for frontier life, unlike European uniforms. The capot was also widely worn by Indigenous people and enslaved Africans and became a symbol of cross-cultural exchange and adaptation in colonial dress (White 2012, 217-18).

One figure even appears with a bow and arrow, joining a Quapaw war party. The French village, placed at the margins of the composition, is clearly peripheral to the central military action. The scene presents the French not as dominant colonizers, but as dependents—under the protection, rather than in control, of their Quapaw neighbors (Arnold 2000; Evans 2024).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/m4P0Z0EZFGhFDBfffdx9m.png" alt="" loading="lazy" decoding="async">
  <figcaption>The "Three Villages Robe," housed in the Musée du Quai Branly-Jacques Chirac in Paris, is a rare indigenous artistic representation of European settlers in Arkansas. This segment of the image, rendered on painted buffalo hide, features the French settlement of <em>Poste des Arkansas</em>, situated adjacent to several Quapaw villages in the lower Arkansas Valley.</figcaption>
</figure>

The world of French Arkansas was deeply connected to that of the Quapaw, though the precise nature of that relationship is debated among scholars. One useful point of comparison lies in patterns of intermarriage. In the seventeenth and early eighteenth centuries, such unions between French men and Indigenous women were relatively common among nations east of the Mississippi, such as the Illini confederacy. These marriages—whether formalized through Catholic sacraments or not—were often mutually advantageous and did not disrupt prevailing gendered norms of lineage and succession. In many of these matrilineal societies, marriage to a French man could bring material or political benefits without severing the bride or her children from her clan or kinship network. In this way, European patriarchal structures could be layered onto Indigenous systems of belonging without entirely displacing them.

Quapaw society, by contrast, was (and remains) patrilineal: clan affiliation is inherited through the father. Some scholars have pointed to this difference as a possible reason for the relative scarcity of recorded Quapaw–French marriages in the Catholic registers of Arkansas. It is likely that many of the women identified simply as “Indians” in those records were not Quapaw, but rather enslaved captives from nations farther west. Others, however, have emphasized the fragmentary nature of the archival record, the possibility that some of these unnamed “Indian” women were indeed Quapaw, and the widespread prevalence of non-sacramental marriages in the region.

Highlighting these historical realities can help us push back against enduring tropes from the nineteenth-century United States—tropes that imagined the American West as sparsely populated by Indigenous peoples and backward Frenchmen, and thus ripe for the taking. Such narratives underpinned the ideology of Manifest Destiny, justified Indian Removal policies, and fueled the U.S. government’s widespread rejection of land claims brought by French- and Spanish-speaking families in the Louisiana Territory throughout the nineteenth century.

Certainly, there were French–Quapaw marriages. Among the most well-known descendants of such unions was the son of François Sarazin (most commonly rendered “Saracen” today), who served as an interpreter for the Quapaws. Identified as a “half-breed Quapaw” in the 1824 treaty he helped negotiate with the United States, Saracen became a key spokesperson for the tribe in its dealings with the federal government. However, he was not universally accepted within the Quapaw Nation as a legitimate or permanent representative. Notably, though, his critics did not question his identity as a Quapaw (Bandy, "Who was Saracen?").

There is evidence that Quapaw patrilinealism was not so rigid as to exclude the naturalization of men with French paternal ancestry into the nation—especially in the context of steep population declines following European contact. By the late nineteenth century, variations of surnames such as Imbeau, Dardenne, Desruisseaux, Coussot, Tousey, and Vallière appear alongside names like Red-Eagle, Buffalo, and Sin-Tah-Hah-Hah on the 1890 Quapaw roll. Commissioned by the federal Office of Indian Affairs and approved by Quapaw chiefs and councilors on the tribe’s Oklahoma reservation, this roll reflects the enduring presence of French-Quapaw kinship networks (Toudji 2011).

American settler colonialism brought rapid and disruptive changes to Arkansas Creoles’ relationship to the land and to the Quapaw Nation. That many of the same names appear on the Quapaw roll of 1890, on nineteenth-century land grant petitions, and on Catholic grave markers—especially at St. Mary’s near Pine Bluff—suggests that families were divided in the wake of U.S. territorial expansion. Some sought to secure land rights through treaties negotiated between the U.S. government and the Quapaw Nation. Others—whether or not they succeeded in claiming land—followed the dispossessed Quapaw to new territory, where they were adopted as kin.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/XHZeKOBRL8u1uQLpu8hMa.jpg" alt="" loading="lazy" decoding="async">
  <figcaption><em><strong> image: </strong></em><em>George Caleb Bingham’s 1845 painting Fur Traders Descending the Missouri (Metropolitan Museum of Art) depicts voyageurs returning with trade goods, including a rare black fox. Originally titled "French-Trader, Half-breed Son," the work has, since its 1935 exhibition at the Met, captivated American audiences and reinforced enduring stereotypes of the French voyageur as “in tune with wild nature” and apart from “civilization” (Korhauser and Mahon 2014).</em></figcaption>
</figure>

[↑ Back to Contents](#contents)

<a id="la-petite-roche"></a>
## "La Petite Roche"

One of the ways we encounter history in our daily lives is through the names of the places around us. At first glance, Central Arkansas appears to celebrate its Creole heritage through its place names. French or French-sounding names abound. But these markers reveal as much about the region’s actual past as about how that past has been repackaged. More prominent, in many cases, are newer “French” names that evoke chic foreign branding. Rather than serving as sites of remembrance, the layering of forgetting and rebranding around Central Arkansas’s “French” place names enacts a spatial version of what anthropologist Michel-Rolph Trouillot called the “silencing” of the past (Trouillot 1997).

One of the most important examples of this phenomenon is the narrative surrounding the original “Little Rock” itself. La Petite Roche Plaza is named for the outcropping observed by French explorer Jean-Baptiste Bénard de La Harpe in 1722, who is also honored. During the Little Rock school integration crisis in 1957, city planners named a new boulevard—meant to speed access to downtown from the growing western suburbs—after La Harpe, who never set foot in what is now Little Rock or established a settlement here. We learn little about the many interpreters and crew members—Indigenous and mixed-ancestry—who made his expedition possible.

The suburban developments branded as “Chenal” offer another kind of example. In the 1990s, developers coined the spelling “Chenal” to give an upscale shopping boulevard a French-sounding name. The road connected Little Rock to Highway 10, which winds westward toward Petit Jean Mountain. The name was a rebranding of nearby Shinall Mountain (itself a corruption of “Chenault”). To heighten the effect, they added street names like “Chenonceau,” referencing the famous Loire château.

Brothers Elijah Nelson Chenault and Benjamin Franklin Chenault, descendants of French Huguenots, arrived from Alabama in the 1850s as English-speaking migrants and purchased land in the area. To my knowledge, there are no street names in the city honoring the Creole settlers who were already here in 1820, when the town gained its first U.S. post office.

These twentieth-century projects, which we cannot remove from their broader context of urban renewal and “white flight” during the Civil Rights Era, carry a particular irony. In aiming to celebrate European founding figures or borrowing glimmers of Frenchness in branding schemes, they further buried the memory of the French-speaking individuals and families who really lived and worked in the Little Rock region before and during the early years of American annexation...

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/ZELU4qjTgHt4q7LogEquz.jpg" alt="" loading="lazy" decoding="async">
  <figcaption><em><strong>Image:</strong></em><em> </em><em>“Photograph of the La Petite Roche Sign,” undated, Downtown Little Rock Partnership records, 1984–2020 (UALR.MS.0294), University of Arkansas at Little Rock Center for Arkansas History and Culture.</em></figcaption>
</figure>

<a id="le-petit-rocher"></a>
### Le Petit Rocher

The site of the modern city of Little Rock sits at a natural narrowing bend of the Arkansas River, where the foothills of the Ouachita and Ozark Mountains rise up from the flat alluvial plains of the Mississippi Delta to the east. Although no permanent French settlement existed at the present-day site of Little Rock, Arkansas Creoles regularly navigated this stretch of the river and established camps along its banks.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/1VKe-Uytk9AxzWo1c3TGI.png" alt="" loading="lazy" decoding="async">
  <figcaption>Detail from a map published in Philadelphia in 1810, based on Zebulon Pike’s explorations along the Arkansas River, identifies a cluster of “French Hunters” near the present-day site of Little Rock (<a href="https://www.raremaps.com/gallery/detail/83485/the-first-part-of-captn-pikes-chart-of-the-internal-part-o-pike">RareMaps.com listing</a>)</figcaption>
</figure>

French speakers referred to the smaller outcrop of rock—situated opposite the larger formation that La Harpe had called <em>le rocher français</em> (“the French Rock”)—as <em>le petit rocher</em>. This is not to be confused with <em>La Petite Roche</em>, the phrase widely used in contemporary signage, which is in fact a mid-20th-century invention (Worthen 2023). <em>Le petit rocher</em>, rendered in English as “the Little Rock,” was the name used for the landmark that marked the western boundary of the Quapaw reserve in the 1818 treaty.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/GWwljGN3TmV7iy-DulBez.png" alt="" loading="lazy" decoding="async">
  <figcaption>Extract from an 1825 letter, in French, of Antoine Barraqué, French-born US government agent among the Quapaw, to George Izard, governor of Arkansas Territory.</figcaption>
</figure>

Despite the wave of Anglo-American (and other) migrants unleashed by the Louisiana Purchase, the Arkansas Valley did not cease to be a Creole space overnight. In 1830, a French priest, Father Martin, composed a census of Catholics living along the Arkansas River. The report listed 38 “whites” and 3 “blacks” in “Petit Rocher,” most of whom would have been French speakers.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/Ei2ZCTxuPCjUpUyse4uJq.png" alt="" loading="lazy" decoding="async">
  <figcaption><em><strong>Above</strong></em><em>: Extract from an 1832 letter, in French, by Father Saulnier, communicating Fr. Martin's 1830 "census" of Arkansas Catholics (Saulnier 1832).  </em><em><strong>Image:</strong></em><em> Downtown Little Rock and Arkansas River bridges, as seen from Knoop Park, 2025. Author’s photo.</em></figcaption>
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/zFRYVXIMq3BKJBzmhKxOV.jpg" alt="" loading="lazy" decoding="async">
</figure>

<a id="french-speaking-settlers-in-little-rock"></a>
### French-Speaking Settlers in Little Rock

The French presence along the Arkansas was not limited to the Post, near its confluence with the Mississippi. Historical records show that French-speaking families were settling along the river in what is now Pulaski County as early as the late eighteenth and early nineteenth centuries.

Rather than disappear or relinquish their lands after the Louisiana Purchase and the establishment of Arkansas as a U.S. territory, many of these families found ways to retain their claims or sustain their households—whether by selling to American speculators or by remaining and contributing to the “improvements” new owners sought to make on the land. Although they were not as successful in these efforts as their counterparts in places like Detroit, St. Louis, or the Illinois Country, Arkansas Creoles demonstrated notable resilience under the American regime.

<figure class="interactive-map">
  <iframe src="maps/little-rock-creole-settlers.html"
          title="Interactive map of French-speaking settlers in Little Rock"
          loading="lazy"
          allowfullscreen></iframe>
  <figcaption>Interactive map of French-speaking settlers, claims, and landmarks in the Little Rock region.</figcaption>
</figure>

We can determine with some certainty the approximate locations of French-speaking families in the early nineteenth century, as documented in property records maintained by the territorial government. One such individual was Jean Baptiste Imbeau, whose presence in the region dates back to the mid-eighteenth century. He initially lived south of the river before relocating to the north side. His son, François Imbeau, owned land on both banks and later settled near a grist mill built by Daniel Wright, about a mile and a half from the small settlement of Little Rock.

In 1825, Wright obtained a deed to the land, which included stipulations for “improvements”—a central concern of the American government. These improvements included enlarging the mill, cultivating orchards, maintaining a residence on the property, and establishing a brickyard closer to town.

Joseph Bartholomew (Barthélémi) settled on the north side of the river, while Louis Bartholomew established himself to the south. The Coussat family also held riverfront properties, with Pierre Coussat owning land along the southern bank. Peter Lefèvre Jr. developed part of Jean Baptiste Imbeau Sr.’s former claim north of Little Rock into a significant plantation, which he later passed down to his children. Other settlers—including Martin Imbeau, Joseph Duchassin, and Joseph Leshee—also contributed to the growth of the community, though the precise locations of their properties remain uncertain. Many of these men can be found in the histoical record having Anglicized their first and even last names (Ross 1956, Ross 1957).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/rNnCrzfXt2yfaH-rF4pHS.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption>Ambrotype portrait of Francis Godfrey Le Fevre (1800–1862), son of Pierre (“Peter”) Le Fevre. Photographer unknown. 3¾ × 3¼ in. Historic Arkansas Museum, Gift of Mr. and Mrs. A. Howard Stebbins III, accession no. 95.035.0005.</figcaption>
</figure>

<a id="creole-land-claims-and-the-1818-quapaw-treaty-line"></a>
### Creole Land Claims and the 1818 Quapaw Treaty Line

Part of the logic behind the 1818 treaty between the United States and the Quapaw was that white settlers should not be allowed to encroach on land reserved for the Quapaw Nation—land demarcated by an actual line running south from the Little Rock outcropping itself. The 1824 treaty, by allowing eleven property-holders who were not Quapaw members per se but labeled “Indian by descent” to retain land on the east side of that line, more or less confirmed the earlier logic—and reinforced the notion that families of mixed European and Indigenous heritage could not, and should not, be construed as fully equal to American citizens.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/X7i_jMaxuvw0K5WWZIJpI.png" alt="" loading="lazy" decoding="async">
  <figcaption>The Quapaw Line, surveyed in the early 1800s, divided Quapaw land from white settlement. Its traces remain visible in Little Rock’s River Market and Quapaw Quarter neighborhoods.</figcaption>
</figure>

It also created a unique scenario: members of a community who had long claimed (and been recognized as) white subjects under French or Spanish rule now found it expedient to assert Indigenous ancestry—depending, it seems, on which side of the line their land claims happened to fall. Two of the individuals named in the 1824 treaty, François Imbeau and Joseph Duchassin, held land near present-day Little Rock; the other nine were located closer to Pine Bluff. Among them were brothers Jean Baptiste Imbeau fils (the younger) and François Imbeau, whose claims were formally confirmed by the treaty. Yet these brothers were not themselves of Indigenous ancestry—their parents, both of French background, had married in New Orleans during the French colonial period. Instead, their eligibility under the treaty appears to have rested on their marriages to sisters Marie Kebed and Thérèse Kebed, whom they wed in Catholic ceremonies at the Arkansas Post just months apart in 1797.

The sisters were daughters of Joseph Barthélemi Kebed (or Quebec), a Canadian immigrant, and Marguerite, identified as “an Indian.” Marguerite was not from the local Quapaw nation but was listed as <em>Cances</em>, a term referring to the Lipan Apache—one of many western Indigenous groups whose members were often captured and enslaved, either by the Spanish or by allied Native nations, to meet the demand of French frontier settlers for both physical and reproductive labor. The fact that she bore a Christian given name suggests she was baptized Catholic at some point.

One of the Jean Baptiste Imbeaus sold his land in 1816 to William Russell, a land speculator from St. Louis who was in the area seeking land or pre-emption rights. Unlike his brother, who remained in Little Rock, Jean Baptiste Imbeau Jr. lived further east and gradually assimilated into Quapaw society. He took on the name White Elk and is remembered as one of those who followed Sarasin back to Arkansas from the land among the Caddo, where the Quapaw had first been forcibly removed by the U.S. government. Two brothers, two similar marriage situations, two very different trajectories.

Nearly a decade after Arkansas became a U.S. territory in 1819, members of the old Arkansas Creole families still appear in records from the Little Rock area—and some of their descendants remain there today. Though increasingly outnumbered by newcomers from the United States, several Creole names are listed on the oldest extant tax roll for Pulaski County, an auditor’s copy dated July 16, 1828. These names, rendered phonetically in English—apparently as the sheriff and tax collector, Samuel M. Rutherford, heard them—include: Bartholomew (Jos., Joseph, and “Madam”), Darden (Abram and Francis), Duchassin (Joseph and Antoine), Imbeau (Alexander, Francis, Martin, Alexander, and Joseph), and Lefevre (Ambrose, Akin, and John), with a second listing for Lefevres (Godfrey and Terrise).

Only one of these French residents was recorded as owning slaves—an auspicious sign of personal wealth and influence at the time (Governor George Izard, for example, owned four). “Terrise Lefeve” (Thérèse Lefevre) was listed as the owner of two enslaved servants: one over the age of ten, and the other between the ages of 16 and 46, according to the categories used in the tax roll. Their gender and names were not recorded. These two individuals are likely among the three “blacks” designated as Catholics in Little Rock by Father Saulnier in his 1830 report.

(Sources: Arnold 2015a; Ross 1956; Ross 1957; Williams, n.d.)

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/zgBO5ccI6qYOi-S7_HZk8.jpg" alt="" loading="lazy" decoding="async">
  <figcaption><em><strong>Image:</strong></em><em> 1872 map of Jefferson County, Arkansas, created by real estate broker W.H.D. Wilson. The map highlights land divisions and ownership, offering a snapshot of the county’s layout and land management in the late 19th century. Courtesy of the Library of Congress, Geography and Map Division.</em></figcaption>
</figure>

<a id="haitian-revolution-emigr-s"></a>
### Haitian Revolution Emigrés

There were also more recent Francophone migrants to the region in the early nineteenth century, including refugees from the Haitian Revolution (1791–1804). Those events had transformed the notoriously violent French-colonial slave society of Saint-Domingue into the nation of Haïti,  independent of France and beacon of freedom in a region where slavery remained the norm. Indeed, the same period saw the expansion and entrenchment of slavery  across the United States, including into territories west of the Mississippi. And that expansion was fueled, in part, by an influx of émigrés who fled the French Caribbean, who often brought enslaved servants with them, along with pro-slavery convictions.

In fact, Arkansas (as part of the Louisiana Territory) would owe its annexation by the American republic to the defeat of the French Army in Haiti. The Louisiana Territory, which had passed from French to Spanish control in 1767, had been quietly returned to France in 1800 through backdoor diplomatic negotiations. As President Jefferson suspected, Napoleon Bonaparte had harbored secret ambitions to rebuild France’s empire in North America, with a reconquered and subdued Saint-Domingue at its center. But the disastrous defeat of French forces in the Haitian Revolution forced him to abandon those dreams—paving the way for the Louisiana Purchase. In 1803, Bonaparte sold the vast Louisiana Territory, including what is now Arkansas, to the United States.

Had Bonaparte succeeded in subduing the Haitian people and reestablishing slavery on the island, Arkansas might have remained a territory of the French empire. Decades later, partisans of secession in Arkansas, like their counterparts across the South, would invoke the memory of the Haitian Revolution to justify the entrenchment of slavery. "San Domingo" remained a name to conjure with, and an effective bugbear for stoking planter paranoia and framing abolitionism as a threat to social order.

Arkansas would have owed their awareness of the Haitian Revolution in part to the influx of Saint-Dominguan émigrés to the United States. The Haitian Revolution triggered several large waves of migration to U.S. port cities. Ultimately the city that would receive the most refugees was New Orleans. Some  moved further up the Mississippi, settling in places like Natchitoches, Louisiana, and St. Louis and Ste. Genevieve, Missouri. Yet Arkansas is typically left off the map of the Haitian refugee diaspora.

As historian Rafe Blaufarb has noted, exiles from the French Caribbean integrated into older Francophone families and business networks in the Mississippi and Ohio River valleys. They drew on shared linguistic and legal frameworks to reestablish themselves sometimes as planters but also as frontier settlers, land speculators, and entrepreneurs. At Arkansas Post, Charles-François Vaugine de Nuisement, whose mother had owned property in Saint-Domingue before the Revolution, exemplifies this pattern. A copy of his father’s 1794 New Orleans will, which mentions this property, is preserved in the Digital Collections of the University of Arkansas Libraries in Fayetteville.

Arkansas Creoles were also involved in efforts to seek assistance from the U.S. government. The Vine and Olive Colony was established with Congressional support to promote viticulture and olive cultivation on former Choctaw lands in Alabama, at the confluence of the Tombigbee and Black Warrior Rivers. Composed largely of middle-class refugees of the Haitian Revolution, many of whom had already begun to rebuild their lives in cities like Philadelphia and New Orleans, the colony offered more than agricultural opportunity. For participants, it represented a chance to reestablish the racial and economic order they had lost in the Caribbean. They invested in enslaved labor and carried with them the cultural, commercial, and racial legacies of Saint-Domingue. Among those listed as members and allotment grantees were three prominent French-speaking residents of Arkansas—Charles-Melchior de Villemont, Charles-François Vaugine de Nuisement, and Joseph Bogy (kin by marriage) (Blaufarb 2016, 27, 191).

Several families of Haitian Revolution refugees settled in Arkansas through more roundabout ways during the nineteenth century. Among them was the Thibault family, whose name survives today in the name of a road southeast of Little Rock, on Fourche Island. Félix Thibault and his brothers were the children of émigrés who had fled from Léogâne (in present-day Haiti) to Philadelphia in the 1790s, where the family became successful silversmiths. Félix eventually settled on Fourche Island in Arkansas. Notably, short story writer David Thibault (1892–1933), one of Arkansas’s most influential literary figures, was born on this plantation and spent much of his life there—though the original buildings no longer survive.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/DbTuK1WRBarCnMU1QlB5x.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption>Brand engraving from Thibault Brothers Co., silver coin flatware, Philadelphia, 1810-1836</figcaption>
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/6I75JG6GSvmBvvIbt1vZL.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption>The Thibault House (courtesy of the UA Little Rock Center for Arkansas History and Culture).</figcaption>
</figure>

The Thibaults may have been the most influential descendants of Haitian Revolution émigrés in Arkansas, but they were not the only ones. U.S. census records reveal several others with roots in Saint-Domingue who made their way to Arkansas in the nineteenth century. A couple named Marchand, originally from the colony, lived in Little Rock. In 1850, a resident of El Dorado was counted with his wife, Marie, born in Saint-Domingue. In 1880, a Haitian-born preacher named Israel Derricks appears in the historical record, living in Hot Springs.

The Morin family, also from Saint-Domingue, became prominent slaveholders in Monroe County. In 1858, the Arkansas Supreme Court heard a case brought by a woman named Morin, identified as “a refugee from the Island of St. Domingo,” who was suing another party over ownership of slaves, possibly brought from the island as well (Jones 2021). The full context of this case remains unclear, but further research in the county papers of Monroe County may shed more light on the lives and legacies of these early Haitian Arkansans (Arkansas Supreme Court 1858, 520).

DeMun Township, in Randolph County  (Arkansas), was named for Lewis (Louis) de Mun, a French émigré from a Saint-Domingue plantation family who fled the Haitian Revolution and settled with relatives in Missouri. Apprenticed as a draftsman to architect Benjamin Henry Latrobe, de Mun was drawn into Aaron Burr’s 1806 expedition, designing boats for the descent of the Ohio and Mississippi. By 1813 he was overseeing a grist and sawmill on the Black River (perhaps the first in Arkansas), listed on the 1815 territorial tax rolls as “Mun &amp; Co.” In 1815, with Lawrence County newly formed, he and his brothers became key figures in the establishment of Davidsonville, the region’s first planned county seat, which included a courthouse, post office, and federal land office. De Mun later returned to Ste. Genevieve, Missouri, where he and his family joined the French Creole elite (McLeod 1944; Lawrence County Historical Society 2017).

[↑ Back to Contents](#contents)

<a id="looking-for-petit-jean"></a>
## Looking for Petit Jean

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/E6R7BeCEEOnDKT97i_MCQ.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption>View of Arkansas River from Petit Jean Mountain (Author's Photo)</figcaption>
</figure>

The Petit Jean River—and the mountain that bears its name—offers a striking example of the cultural erasure, intentional or not, that accompanied generations of Anglo-American settlement. By the late nineteenth century, romantic legends had emerged to explain the name’s origin. In one version, Petit Jean is a young woman who disguised herself as a cabin boy aboard a French ship to follow her lover to <em>Louisiane</em>. In another, Jean is a French Revolutionary émigré driven mad by the loss of a family member. Both versions feature the help of friendly but nameless “Indians” and a lingering spectral presence—evoking a nostalgic vision of a bygone era when French settlers and their Native allies left only a fleeting, almost ghostly, imprint on the land, soon overtaken by Anglo-American expansion.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/3HodeIZIj5zuy_64XXES7.jpg" alt="" loading="lazy" decoding="async">
  <figcaption>Marker, "The Legend of Petit Jean," Petit Jean Mountain, 2024 (Author's Photo).</figcaption>
</figure>

<a id="a-legendary-brand"></a>
### A Legendary Brand

As many Arkansans will tell you, Petit Jean is the crown jewel of the state park system—Arkansas’s oldest park and one of the most popular in the South, drawing over 800,000 visitors annually. But its iconic status didn’t happen overnight. Petit Jean has been carefully developed as a tourist destination for more than a century. Today, the name itself is a recognizable brand, appearing on everything from craft brewery labels to artisanal butcher products.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/G48Ig3XUrQNZRyWPeyyfl.png" alt="" loading="lazy" decoding="async">
  <figcaption>Petit Jean Pilsner, Point Remove Brewery (<a href="https://pointremovebrewingcompany.com">https://pointremovebrewingcompany.com</a>)</figcaption>
</figure>

Petit Jean’s breathtaking scenery and relative isolation also made it a retreat for gentlemen farmers in the twentieth century—including, beginning in the 1950s, the homestead of one of Arkansas’s most influential political figures, Winthrop Rockefeller, who served as governor from 1967 to 1971 (Kirk 2022).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/GqwHaUqPdLMr9IRBN3ibH.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption>1966 Time Magazine cover featuring an illustration of Winthrop Rockefeller on Petit Jean Mountain.</figcaption>
</figure>

<a id="the-real-petit-jean"></a>
### The "Real" Petit Jean?

With all the mystique surrounding the mountain, it’s tempting to dismiss the many versions of the Petit Jean legend—the story of its namesake—as pure fabrication. Indeed, some scholars have done just that. It’s true that one would search in vain for the supposed “French” names of the legend’s key figures in ship manifests, early censuses, or sacramental registers. Yet, as with many enduring legends, a grain of truth often lies at the core. So we’re left to wonder: was there ever a historical figure named Petit Jean?

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/2su9ycCp4fmIj0QmHA0XP.jpg" alt="" loading="lazy" decoding="async">
  <figcaption>Petit Jean Grave Site in 2019 (Author's Photo).</figcaption>
</figure>

Historian Morris Arnold has proposed what is arguably the most plausible theory about the figure behind the name. Arnold locates an explicit mention of a “Petit Jean” in a French document describing an Osage attack on a French hunting party along the Arkansas River in the 1730s, upriver from Arkansas Post (Arnold 1994, ).

As Arnold notes, “Petit Jean” (French for “Little John”) was a popular nickname among eighteenth-century French soldiers and settlers, and multiple individuals bearing this name appear in documentary records across the region. Still, the "Petit Jean" of the 1730s stands out as the most likely candidate for the river and mountain’s namesake, due to striking parallels between the archival references and oral traditions that surfaced nearly a century later.

So who was this Petit Jean, and what were the circumstances of the violent episode in which his name appears?

<a id="contested-sovereignty"></a>
### Contested Sovereignty

In the early 1730s, relations between the French and the Osage Nation were becoming increasingly strained. Although the Osage had long maintained positive ties with the French—indeed, a delegation had traveled to Paris and been formally received by the regent at Versailles in 1725—tensions soon emerged. By 1730, the Osage were growing resentful of the rising number of French fur traders and bear oil hunters venturing upriver from Arkansas Post into territories the Osage claimed as their own hunting grounds.

In 1732, according to French records, a group of Osage warriors launched a surprise attack on a French hunting party along the Arkansas River. The ambush took place at a contested stretch of the river, a zone disputed among the Osage and neighboring Indigenous nations.

When no word came back from the hunting party, the commandant at Arkansas Post sent a report to his superior in New Orleans, stating that all eleven members were missing and presumed dead—a detail that suggests he was aware the expedition had entered contested territory. In reality, the Osage had struck while most of the party was away from their riverside camp, killing two servants whose bodies were discovered upon the others’ return. Confused and terrified, the surviving hunters chose not to return by the usual route down the Arkansas River. Instead, they undertook a harrowing overland journey on foot through the Ozarks, heading north to the nearest safe French settlement in the Illinois Country.

Colonial officials in New Orleans initially concluded that such an affront could not go unpunished. Plans were set in motion to mobilize a force of French soldiers and Native allies to exact revenge. But their stance shifted dramatically once the full truth emerged—particularly the details of what had actually occurred, and who the victims truly were.

<a id="the-documents"></a>
### The Documents

Only a handful of official reports—authored at the highest levels of French colonial administration—survive from this incident. These documents reveal much about the priorities of imperial architects and their agents in the distant outposts of empire, but they must be read critically and between the lines to uncover the motivations and actions of those on the ground.

The 1732 attack and its aftermath amounted to a diplomatic crisis of significant consequence for the fragile French presence—over 500 winding miles up the Mississippi River. The French were still reeling from what they saw as the "treachery" of the Natchez, who, in 1729, had launched a devastating reprisal against French settlers, killing some 230 people and unraveling much of France’s carefully woven web of alliances in the region. In the wake of such violence, French officials were left to ask: who among their Native allies could still be trusted?

Naturally, news that eleven French subjects had gone missing from Arkansas Post—presumed dead at the hands of a Native nation—alarmed colonial officials. But by the spring of 1734, the narrative had begun to shift. In an April dispatch to France, Louisiana governor Bienville clarified the situation:

<blockquote>"The news that I had the honor of sending to Your Greatness, regarding the letters I had received about the murder of eleven canoemen (voyageurs), of which the Ozages [sic] were accused, has only been partially confirmed."</blockquote>

By July, he issued another update, further walking back the original report:

<blockquote>"It was reported that [Osage] Indians had killed 11 Frenchmen, but it turned out that they had only killed a slave and a man named Petit Jean, who was Bohemian."</blockquote>

This revision not only de-escalated tensions but also laid bare the fluid and hierarchical logic of French colonial value systems—where the lives of enslaved people and men like Petit Jean, a likely marginal figure, were not afforded the same weight as those of full French citizens.

In fact, as soon as they heard the accusations from Arkansas Post, the Osage acted swiftly to manage the fallout and present their version of events. They informed French traders in the Missouri region—the heart of their territory—to relay their regrets to the commandant at Arkansas Post, Pierre-Louis Petit de Coulanges. They even dispatched a delegation directly to the Post, offering compensation equal to the value of the enslaved man who had been killed.

The Osage acknowledged responsibility for both deaths. However, regarding the second victim—“Petit Jean”—they insisted repeatedly that they believed him to be a slave and an Indian (<em>sauvage</em>). They emphasized that they had never intended to harm, in their words, “any Frenchman.”

---

<em><strong>Below are translations of extracts from the two reports  mentioning Petit Jean.</strong></em>

Several terms are essential for understanding these documents in context. Among them are "<em>Voyageur" </em>and <em>"Engagé." Voyageurs </em>were officially licensed canoemen tasked with transporting goods between posts. <em>Engagé</em> refers to indentured servants employed by voyageurs, responsible for a range of duties from paddling and maintenance to navigating and setting up camp. These terms defined roles within the fur trade in Louisiana and New France. Lewis and Clark, on their expedition, employed <em>engagé</em>s to crew their canoes and manage their camps. Petit Jean was described in one part of the governor's report that he had been <em>engagé </em>with the<em> voyageurs.</em>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/ym12l-3BJYPO5dgW8s38E.jpg" alt="" loading="lazy" decoding="async">
  <figcaption>It may not be possible to recover the specific contract whereby Petit Jean became “engaged” to provide services for <em>voyageurs</em> along the Arkansas, but this document offers a close parallel. Drawn up in New Orleans in 1746, it records the voluntary engagement of two men, Louis Dardenne and Jean Saguin, to accompany the <em>voyageur</em> “<em>Sieur</em> Pierre Clermont on the [hunting] trip he will take in Arkansas (<em>aux arkansas</em>).” Like many such agreements in the French colonial world, the contract specifies the terms of service—one year of labor in exchange for provisions during the voyage and monetary wages upon return. It also reveals the unequal power dynamics underpinning these arrangements. The <em>engagés</em>, who declared that they could not sign their names, are not accorded the honorific “sir” given to Clermont; they agree to obey all that he will “order” them to do for the duration of the contract. Source: “Cantrelle Witnesses a Letter for Engagés,” March 10, 1746, Colonial Arkansas Post Ancestry Collection, University of Arkansas Libraries.</figcaption>
</figure>

#### Letter of Governor Bienville to Minister of the Navy, the <em>comte </em>de Maurepas, New Orleans, April 22, 1734 (ANOM C13A, XVIII, folios 145-146):

<blockquote>"The news that I had the honor of sending to Your Greatness, regarding the letters I had received about the murder of eleven canoemen (<em>voyageurs), </em>of which the Ozages (<em>sic</em>) were accused, has only been partially confirmed. It is true that they killed a slave and a Bohemian, in the service of (<em>engagé avec) </em>the hunters, whom they mistook for an Indian. The others, who were away when this act was committed, were terrified when they returned to the campsite (<em>cabannage</em>) where the murder had taken place. Not daring to trust any [indigenous] nation, they decided to make their way to the Illinois country over land, where they arrived after two months of walking. Consequently, the officer commanding at the Arkansas Post [Pierre-Louis Petit de Coulange], not seeing them return, determined that they had been killed and informed me as such.<br/><br/>These Ozages, upon hearing via the Missouri River that Mr. d'Artaguiette was resolved to lead nations against them to avenge this murder, instructed the traders at the Missouri [Post] to offer apologies on their behalf and to assure him that they had not intended to Frenchmen and that they would gladly submit to anything he would demand from them. Not content with only that, they even went to the Arkansas Post to present their apologies to the officer in command there and covered [the cost] of the death of the slave in such a manner that I do not believe it appropriate, given the state of our affairs, to pursue this matter further. We do not need to seek out new wars; we have learned that one has just broken out in Canada, in which the Illinois country will likely play a major part."</blockquote>

<em><strong>Later, a summary report on the state of French relations with various indigenous nations, included an abbreviated version. </strong></em>

<strong>Letter of Governor Bienville to Minister of the Navy, the </strong><em><strong>comte </strong></em><strong>de Maurepas, New Orleans, July 27, 1734 (ANOM C13A, XVIII, folios 225-226v):</strong>

<blockquote>"It was reported that [Osage] Indians had killed 11 Frenchmen, but it turned out that they had only killed a slave and a man named Petit Jean, who was Bohemian. When they [the Osages] learned that Mr. [Diron] Dartaguiette [Inspector General of Louisiana] was planning to mobilize the nations against them to avenge this murder, they instructed the traders to apologize to him on their behalf, and assure him that they had not intended to kill any Frenchmen and that they were willing to accept any recompense he would ask of them. Not content with that, they went to the Arkansas Post to apologize to the officer in charge and cover [the cost] of the death of the slave. Thus, he [Pierre Louis Petit de Coulange, commandant of Arkansas Post] does not believe it necessary to pursue the matter any further, considering the current state of affairs."</blockquote>

In the margin, the mark of the Minister himself: <em>"Approved. Continue to keep [me] informed."</em>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/TRko1VVYDbRXLDhwQ2zWb.png" alt="" loading="lazy" decoding="async">
  <figcaption>Letter of Governor Bienville, New Orleans, 27 July 1734. in Archives Nationales d'Outre-Mer, COL C12A, fol. 226v (Author's Photo, taken in the Microfilm Gallery of the Archives Nationales, CARAN Site, Paris)</figcaption>
</figure>

But what does it mean that Petit Jean is described in both documents—as one might say, the first directly, the second indirectly—as a <em>Bohème</em>? Why did Governor Bienville believe that once it was clarified the victims of the Osage attack were not eleven Frenchmen but “only” an unnamed slave and a <em>Bohème</em> with no surname, the Minister of the Navy—Jean-Frédéric Phélypeaux, comte de Maurepas, one of the most powerful figures in the French state—would <em>approve</em> of not seeking retribution for the killings?

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/-sdTuxRuC0QkTxzaGuIeW.png" alt="" loading="lazy" decoding="async">
  <figcaption>Detail from the report of Bienville, from the archives of the office of the Ministry of the Navy (now in the colonial division of the French national archives).</figcaption>
</figure>

<a id="roma-in-france-and-its-empire"></a>
### Roma in France and its Empire

In early modern France and its empire, the term <em>Bohème</em> (or Bohemian) was commonly used in official documents to describe members of the Romani diaspora. Individuals identified as <em>Bohêmes</em>—or alternatively as <em>Égyptiens</em> (“Egyptians”), from which the English term “G*psies” is derived—had been classified as <em>personae non gratae</em> in the kingdom of France since the reign of Louis XIV.

Linguistic and genetic evidence traces the origins of the Romani diaspora to India. The Roma began migrating out of South Asia around 1,500 years ago, eventually reaching Central and Western Europe by the 1300s, passing first through Persia and the Balkans. In Europe, they were frequently met with hostility and persecution—and in some regions, were systematically forced into bondage. In Romania, for example, the enslavement of Roma people persisted until its formal abolition in the 1850s (Fraser 1995; García-Fernández et al. 2020; Hancock 2002).

During the Renaissance, a migration of so-called <em>Bohèmes</em> arrived in France. They earned this name because they carried letters of protection from Sigismund, the Holy Roman Emperor and King of Bohemia, who ruled from Prague. Initially, they were not met with particular hostility. In regions such as Lorraine, near the German border, local noblemen extended protection in exchange for entertainment and services. French aristocrats exoticized the Roma, associating their horsemanship, colorful attire, and apparent freedom of movement with the chivalric ideals and pageantry of the Crusader era.

Beginning in the mid-seventeenth century, the Roma came under increasingly systematic persecution by the French Crown. The most sweeping and consequential legislation arrived in 1682, when laws not only ordered the expulsion of <em>Bohemian</em> men and women from the kingdom, but also threatened to strip nobles of their titles if found harboring them—an extraordinary measure by any standard.

Why were the Roma targeted so aggressively? This was a moment when Louis XIV was still consolidating power over a fractious nobility, amid growing anxieties about vagrancy and social disorder. Perhaps most significantly, France was experiencing a major economic crisis—and the <em>Bohèmes</em> became a convenient scapegoat (Filhol 2020).

<em><strong>Images: </strong></em><em>Jacques Callot’s series La vie des Égyptiens is often cited as a record of Roma in early modern France, but his etchings exotified and distorted Romani life. Rather than reproduce these images in their original format, the pieces below are a contemporary reinterpretation. In her textile series Out of Egypt, Polish-Romani artist Małgorzata Mirga-Tas reimagines Callot’s work, offering a layered perspective grounded in Romani experience (see blow). On the right: Jacques Callot, Roma men, women, and children on horseback and on foot, early seventeenth century. Etching and engraving. Metropolitan Museum of Art.</em>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/HEGi8pfAADJzgSrh2qK4K.jpeg" alt="" loading="lazy" decoding="async">
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/ZT8sVT3QUC1SGrebJrZzh.jpeg" alt="" loading="lazy" decoding="async">
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/OGa1U4racCQKvaRFr81jR.jpg" alt="" loading="lazy" decoding="async">
</figure>

<a id="romani-diaspora-in-french-louisiana"></a>
### Romani Diaspora in French Louisiana

Like many individuals arrested and imprisoned during this period, some Romani prisoners were deported to Louisiana to serve in the colonial army or help populate and stabilize the struggling colony. One of the most significant ships to carry Roma from France to Louisiana was the <em>Tilleul</em> (pronounced <em>tee-yeul</em>), which departed from Dunkirk in May 1720 with 341 passengers on board (Mills 2011; Ostendorf 2021). The man referred to only as "Petit Jean" in the 1730s documents may well have arrived in North America on that very ship, which carried dozens of Romani families—grouped in the passenger list by sex and legal status (prisoner or voluntary migrant).

Upon arrival, some of these Romani migrants settled in Pascagoula, near the Biloxi landing site of the <em>Tilleul</em>. Others, later in the century, moved to the Red River region, joining a broader, multinational migration of Gulf Coast Indigenous groups with whom they had originally lived. These communities resettled on the prairies of northwest Louisiana (Mills 2011). For more on naturalization practices and survival strategies among the so-called <em>Petites Nations</em> in the 18th century, see Ellis (2023).

Other Romani individuals settled in the town of New Orleans, from which sporadic military expeditions—including some that featured separate companies of <em>Bohèmes</em>—were mobilized to defend Arkansas Post and the Illinois Country (Vidal 2019).

Could <em>Petit Jean</em> have been one of the several “Jeans” listed as “Bohemian” prisoners on the <em>Tilleul</em>’s passenger list, and who later appear in Louisiana church records—perhaps Jean Gaspart or Jean Christophe? It’s a tempting conclusion. Neither name appears in the documentary record after the 1720s and 1730s, the very period during which <em>Petit Jean</em> is reported to have died.

Both Jean Gaspart and Jean Christophe—if they were indeed separate individuals—were connected to another Romani woman named Marie Agnès Simon. She had arrived aboard <em>Le Tilleul</em> with her first husband, Jean Christophe, and their children. Genealogists have traced connections between the Romani passengers of <em>Le Tilleul</em> and a family in New Orleans who later migrated to Arkansas Post and established roots there: the Sauciers (or Sautiers). In 1732—the same year as Petit Jean’s disappearance—a “Marie, bohemienne” is recorded as residing on their property, located at what is now the corner of Royal and St. Peter Streets in the French Quarter of New Orleans.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/QJz3hyw21ZU1z2mIiueP3.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption>Site of the Sautier Household, at the corner of Royale and Saint Pierre Streets. From "Plan of New Orleans the capital of Louisiana; with the disposition of its quarters and canals as they have been traced by Mr. 
de la Tour in the year 1720" (Detail). Library of Congress).</figcaption>
</figure>

Marie Agnès maintained close ties with other Louisiana <em>Bohèmes</em>. By 1725, she is recorded as the wife of Jean Gaspart—possibly the same Jean Gaspart listed among the passengers of <em>Le Tilleul</em>. However, this figure may in fact be Jean Christophe, her first husband, under a different name. A Jean Gaspart also appears in military records as a drummer serving under Captain Le Blanc, though Le Blanc was not stationed on the Gulf Coast at the time; he had been posted farther up the Mississippi.

Later, Marie remarried—to “Joseph, a Bohemian invalid,” who is listed as her spouse at the time of her death in Mobile in 1743. This raises a lingering question: what happened to Jean, whether Gaspart or Christophe, that left Marie a widow and eligible to remarry?

Although Marie died in Mobile, her descendants eventually relocated to the Red River region of northwest Louisiana—apparently settling near an international community of Pascagoula and Biloxi people who had migrated from their Gulf Coast homelands alongside them. Visitors to the area throughout the nineteenth century, including the landscape architect and journalist Frederick Law Olmsted, continued to note the presence of “Egyptians”—a common term for Roma—both in this inland region and along the Gulf Coast, including Pascagoula. Observers remarked that, like their Native neighbors, the Roma were well known for their skills as carpenters, particularly in building schooners for the coastwise trade along the Gulf (Mills 2011).

<a id="racial-liminality"></a>
### "Racial Liminality"

Scholars Elizabeth Shown Mills and Ann Ostendorf have demonstrated that the Roma of Louisiana, while often assimilated into the white population, were at times categorized separately—or grouped among the second-class <em>gens libres de couleur</em> (free people of color). This ambiguous legal status placed them outside the rigid triad of racial categories used in colonial Louisiana: <em>nègre</em> (Black), <em>sauvage</em> (Indigenous), and <em>blanc</em> (white). It was precisely this "racial liminality," as Ostendorf puts it, that enabled Roma individuals to live and marry in ways that the law did not explicitly permit (Ostendorf 2021, 682).

Indeed, some men and women of Romani background strategically leveraged their racial ambiguity—at least as perceived by colonial officials—to their advantage. One case perfectly encapsulates this phenomenon. In 1725, Marie Jacqueline Gaspart, a woman of Romani descent, married Jean-Baptiste Raphaël, a “Free Black” native of Martinique. Under the terms of the 1724 <em>Code Noir</em> (Black Code), marriage between “whites” and “blacks” was expressly prohibited. Recognizing the legal ambiguity surrounding Marie Jacqueline’s racial classification, the parish priest sought special approval from the governor before performing the ceremony.

While the need for official approval suggests that all parties understood Marie Jacqueline Gaspart to be legally classified as white, the fact that approval was granted is even more telling. This is the first—and only—surviving case of a “white” woman marrying a “Black” man in French-colonial New Orleans. That the exception was made strongly suggests that Marie Jacqueline was not perceived as fully white, likely due to her Bohemian parentage (Mills 2011; Ostendorf 2021). And who was Marie Jacqueline? None other than the daughter of Jean Gaspart and Marie Agnès Simon.

<a id="burying-petit-jean"></a>
### Burying Petit Jean

Bearing these historical possibilities in mind, let us return to Petit Jean. In the end, Louisiana’s governor deemed it more expedient not to pursue retribution for the deaths of Petit Jean and the unnamed enslaved man with whom he had hunted. It was not in the interest of the colony, Governor Bienville reported to his superiors at Versailles. The response from the Minister of the Marine was brief but telling—marked with a flourish in the margin: <em>“Approved.”</em>

The treatment of Petit Jean’s death by French officials—not valuable enough to be avenged, yet not inconsequential enough to be entirely ignored—reveals the peculiar liminal space occupied by members of the Romani diaspora in French colonial Louisiana. It mirrors the paradoxical position they held in metropolitan France: social outsiders, sometimes tolerated or even welcomed, and at other times persecuted and expelled.

More than a century later, an account said to be based on local “tradition” appeared in an 1869 issue of the <em>Arkansas Gazette</em>. The story, reprinted from the fledgling <em>Dardanelle Times</em>, portrayed Petit Jean not as a hunter but as a cook serving a group of soldiers. In French colonial Louisiana, however, the distinction between soldier and hunter was often blurred, since garrison troops frequently supported themselves through hunting and trading. According to the tale, the camp was attacked during the night by a party of Osages—specifically named in the account. Petit Jean’s body was found the next morning on the banks of the river, at the foot of what is now known as Petit Jean Mountain. The soldiers, the story goes, buried him there—giving the mountain its name.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/d-NA_chIViClNh6nBUkE0.png" alt="" loading="lazy" decoding="async">
  <figcaption><em>Daily Arkansas Gazette</em>, Little Rock, Arkansas, November 3, 1869, p. 3. Accessed April 16, 2024. <a href="https://www.newspapers.com/image/131672061">https://www.newspapers.com/image/131672061</a>. It is unclear where the tellers of this tale derived the surname "d'Ambrose," but this would have been a well-known name in the region. Ambroise (or Ambrose) Lefevre (1830s-1889) was a prominent settler in the Arkansas River Valley. The name “Petit Jean” for the tributary confluence in Arkansas appears on published maps as early as 1823. This detail (right) is from Stephen H. Long and Edwin James’s 1823 map, “Country Drained by the Mississippi, Western Section,” from the David Rumsey Map Collection. It was based on Long's observations during his expedition (as part of the U.S. Army's Corps of Topographical Engineers) up the Platte and Arkansas rivers (Hayes 2009, 73). References exist to a "Peté John B[a]yo" in American writings as early as 1813 (Higgins 2019), in the letter of US Indian subagent William Lovely to the Cherokee of Arkansas (Lovely [1813] 1949, 721).</figcaption>
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/9ZxYm2K7rGlhgcbw7fPLq.png" alt="" loading="lazy" decoding="async">
</figure>

<a id="evolution-of-a-legend"></a>
### Evolution of a Legend

So how did the legend change so drastically? Tracing the scattered mentions of Petit Jean as a historical person reveals a complicated lineage—one that, while apparently rooted in fact, gradually took on a life of its own. Over time, the story evolved so dramatically that the most familiar version today—that of a cross-dressing woman from the French colonial period—has dominated public memory for over a century.

Promoters of that version of the story were more invested in attracting settlers—or, later, tourists—than in uncovering the truth behind the legend or exploring the larger historical context it emerged from. In the early twentieth century, for example, Dr. T. W. Hardison—often called the “Father of Arkansas State Parks” for his tireless conservation efforts on Petit Jean Mountain—frequently invoked the legend in his pamphlets and public speeches. For Hardison and others, the romantic tale of a cross-dressing French heroine functioned less as a subject of historical inquiry and more as a powerful tool of place-making and regional promotion.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/uoiqrgjk3bA2hhSuwJpWq.png" alt="" loading="lazy" decoding="async">
  <figcaption>Frontispiece from T. W. Hardison's pamphlet, "A Place Called Petit Jean: The Mountain and Man's Mark," 1955, one installment in a series of brochures promoting the mountain.</figcaption>
</figure>

Various aspects of the female Petit Jean legend—her sacrifice as a white European woman in the wilderness of the New World, her close friendship with peaceful, anonymous Indians who honor her memory—stand in stark contrast to the Native agency and anti-settler violence at the heart of the actual 18th-century incident. In fact, the tale reads almost as an overtly on-the-nose example of what Dakota historian Philip Deloria has called “playing Indian.” This recurring trope in American literature and popular culture, which relies on benign and nonspecific references to Native people, erases the realities of Indigenous presence—historically and in the present. As Deloria argues, such narratives serve to legitimize “Indian Removal” in every sense of the term (Deloria 1998).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/V8bR5h5kr6Kf44NXrKLw7.png" alt="" loading="lazy" decoding="async">
  <figcaption>Extract from Lucille Clerget Rankin's poem, "The Legend of Petit Jean Mountain," published in 1946. Its dedication reads: "to our forefathers, who so nobly blazed those barren trails, that they might give to us the modern civilization which we enjoy today."</figcaption>
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/fsRLjUeJE9pBjOspct8ge.png" alt="" loading="lazy" decoding="async">
</figure>

This was also a period in which many regions across the United States were reviving stories of their French heritage—though often in ways that sanitized and romanticized the past. These commemorations were frequently tied to Franco-American solidarity during the two World Wars. Figures like Joan of Arc gained renewed popularity in the U.S. (Blaetz 2001).

Yet this wave of revisionist memory work tended to flatten the diverse contributions of French-speaking people to the development of the American Midwest. The result was a history of the “French” in the West that tended to erase or sanitize the past, replacing, as Anne Hyde puts it, what was a “biracial and bicultural” space—that is to say, one composed of mixed-ancestry Indigenous–European families—with a narrative dominated by Anglo-American pioneers (Hyde 2011). These narratives also gradually obscured the roles of French-Canadian fur trappers, French adventurers, and mixed French–Indigenous families in the making of the West. This “phantom America” (to borrow a phrase coined by French historian Gilles Havard) was nearly entirely forgotten amid the popularization of “Western” books and films, which left little room for nuanced understandings of the francophone presence in the American West and shaped historical consciousness in Europe as much as in the United States (Havard 2019).

To the extent that it has been undertaken, scholarly work on the Petit Jean legend takes a critical step back from the mythmaking to examine its possible origins and evolution. First published in 1991, Morris Arnold’s rigorously researched <em>Colonial Arkansas</em> became the first scholarly monograph to evaluate the Petit Jean story through the lens of French archival sources. Arnold was the first scholar to identify the 1732 killing of a "Bohemian" by Osage warriors as a likely origin for the river and mountain's name (Arnold 1993). In 1999, DeAnn McGrew authored a rich undergraduate thesis, <em>Origins of the Legend of Petit Jean</em>, preserved at the University of Central Arkansas library, which made use of local newspaper archives to identify the earliest appearances of the legend. She notes 1823 as the possible first appearance of "Petit Jean River" on a map and noted that a town bearing the name, complete with a post office, existed as early as 1831 (McGrew 1999).

Below is a timeline of allusions to Petit Jean in non-academic print sources—ranging from newspapers and tourist brochures to popular nonfiction and poetry. Deconstructing the mythologies that have grown around “Petit Jean” over the centuries offers a way to counteract the romantic erasures of previous generations. By tracing these layers of narrative construction, we can begin to peel back the forgetting that has shaped Arkansas’s geography and distorted our understanding of its early history.

<div class="timeline-entry">
  <p class="timeline-year">1869</p>
  <p>The <em>Arkansas Gazette</em> publishes an article from the <em>Dardanelle Times</em> promoting the area. It relays a local legend: "Petit Jean," a cook serving a "party of soldiers, in search of gold," was killed by Osages. His friends buried him at the site of the mountain, which they named for him. Reference/Author: DeAnn McGrew.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1878</p>
  <p>The <em>Dardanelle Western Immigrant</em> publishes a different version of the legend: a French woman disguised herself as a sailor to follow her lover to the New World; her lover accidentally pushed her overboard into the Petit Jean River, leading to her death by freezing. Could the shift from a male to female Petit Jean have taken place in the decade since the previous article?  Reference/Author: DeAnn McGrew.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1889</p>
  <p>Mrs. Leister E. Presley's Biographical and Historical Memoirs of Western Arkansas, publishes an oral tradition about a "small man whose name was Petit Jean," who engaged in combat with "The Indians." He later died from his wounds while the group he was part of was traveling back down a river. This incident led to the naming of Petit Jean. Reference/Author: Presley.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1905</p>
  <p>Reuben Gold Thwaites publishes volume 13 of his <em>Early Western Travels, 1748–1846</em>, containing Thomas Nuttall’s <em>Travels into the Arkansa Territory</em> (1819). Nuttall himself mentioned the “Petit John” River and its “conspicuous and picturesque” hills but did not comment on the origin of the name. In his edition, Thwaites adds a footnote noting: <em>“Tradition says that the stream is named for a Frenchman of small stature, named Jean, who was here killed by the Indians.”</em> This is the earliest printed version of the Petit Jean naming story, indicating that the tradition was still current in the early twentieth century.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1931</p>
  <p>Fred W. Allsopp publishes <em>Folklore of Romantic Arkansas</em> in New York, in which Petit Jean is mentioned as a French woman stowaway who disguised herself as a man. The event is not placed during the French colonial period but rather, during the French Revolution.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1941</p>
  <p>The WPA's <em>Arkansas: A Guide to the State</em> offers an alternative origin for the name: Jean la Caze, a French nobleman who escaped the Revolution, journeyed to New Orleans and up the Mississippi to Arkansas. His wife and son succumbed to the hardships of the voyage, but La Caze survived, eating berries and playing a flute. Early American settlers were said to encounter him on the mountain, driven insane by his loss.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1946</p>
  <p>Lucille Clerget Rankin publishes several poems, bound as "The Legend of Petit Jean Mountain," in which she cites items found in the Morrilton Public Library and an "oft-told Indian legend" as the sources for the story of Adrienne and Cheves.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1955</p>
  <p>Marguerite Turner publishes "Petit Jean: A Girl, a Mountain, a Community," which expands greatly on the legend of the female Petit Jean, also placing her arrival during the French Revolution.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1955</p>
  <p>An informational brochure repeating a variation on the female Petit Jean theme, but placing her arrival within the French colonial period, is published by Dr. Thomas William Hardison (1884-1957), physician, author, and geologist who made his home on Petit Jean Mountain. Hardison played a pivotal role in the establishment of Arkansas's state park system and Petit Jean as its inaugural property, in 1921.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1970</p>
  <p>Mary D. Hudgins, member of the Arkansas Historical Association, the Arkansas Folklore Society, and the American Association of University Women, publishes a review in the <em>Arkansas Historical Quarterly</em> of Lucile Price Turner's pamphlet, "The Legend of Petit Jean," which takes for granted as common knowledge the female Petit Jean legend and its association with the mountain.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1996</p>
  <p>Multiple versions of the legend appear in Linda E. Clarke's <em>The Legend of Petit Jean.</em></p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">1997</p>
  <p>"The Many Legends of Petit Jean," a blog post signed RJT. Based on interviews with a state park interpreter, Douglass Carter, who claimed the Petit Jean legend was created in the early 20th century by the Stout family, owners of a hotel on the mountain, as a marketing strategy to attract honeymooners. Around 1912 or 1913, they paid three men to create a false cairn and gravesite to lend credibility to their story.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">2001</p>
  <p>Lee Woodard's book, <em>Petit Jean's Mountain: The Origin of The Legend</em>, proposes that Petit Jean was a French nobleman involved in La Salle's expedition who drowned in the Arkansas River in 1687 and was buried near the top of Petit Jean Mountain.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">2011</p>
  <p>Donald Higgins publishes article in the <em>Encyclopedia of Arkansas</em>, in which he argues that “Petit Jean” may be a mis-transcription of <em>Petit Jaune</em> (“Little Yellow”), connecting this to Colonel René Paul’s 1818 Quapaw Treaty map, which labeled today’s Petit Jean River as the “Little Yellow.”</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">2014</p>
  <p>Christopher Theofanidis composes "The Wind and Petit Jean" for the Arkansas Symphony Orchestra, drawing inspiration from the legend of the disguised French woman.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">2016</p>
  <p>William B. Jones and illustrator Gary Zaboly offer a creative take on the lovers at the heart of the legend in their children's book, <em>Petit Jean: A Wilderness Adventure</em>, which features a storyline reminiscent of Longfellow's romantic classic, "Evangeline." Unlike previous versions, it offers accurate details relating to life in French-colonial Arkansas Post and New Orleans.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">2023</p>
  <p>Donald Higgins's <em>Arkansas Encyclopedia</em> entry for "T. W. Hardison (1884–1957)" attributes the creation of the Petit Jean legend to him. After the 1923 establishment of Petit Jean State Park, Hardison worked tirelessly to promote the park through various means including letters, articles, and speeches. His rendition of the "Legend of Petit Jean" gained widespread popularity.</p>
</div>
<div class="timeline-entry">
  <p class="timeline-year">2023</p>
  <p>The Arkansas State Parks website, in an informational brochure for Petit Jean State Park, presents the story of a French woman stowaway, set during the French colonial period.</p>
</div>

[↑ Back to Contents](#contents)

<a id="survival-strategies"></a>
## Mapping Survival Strategies

<blockquote><em>“As we swept away from the shore, I ... prayed that the inhabitants might long retain their happy ignorance, their absence of all enterprise and improvement, their respect for the fiddle, and their contempt for the almighty dollar. ... In a little while the steamboat whirled me to an American town, just springing into bustling and prosperous existence. Alas! with such an enterprising neighbor, what is to become of the poor little Creole village!” </em></blockquote>

— Washington Irving, <em>A Sketch from a Steamboat</em>

This was how renowned New York writer Washington Irving described the Arkansas Post during his 1832 visit—part of a broader tour of the United States' rapidly expanding western frontier. The "American town" referred to Little Rock, upriver from the Post. Published in 1887 as <em>A Sketch from a Steamboat</em>, Irving’s account reveals both the romanticization and condescension that often shaped Anglo-American views of Creole communities in this era: admired for their charm and tradition, yet assumed to be inevitably doomed in the face of capitalist expansion.

Irving was aware of the widely held belief among his Anglo-American contemporaries that the displacement of American Indians and French-speaking Creoles by enterprising Americans was inevitable in the West. Though sympathetic, he shared his countrymen’s patronizing view:

<blockquote><em>"In no part of our country...are the customs and peculiarities, imported from the old world by the earlier settlers, kept up with more fidelity than in the little, poverty-stricken villages of Spanish and French origin, which border the rivers of ancient Louisiana. Their population is generally made up of the descendants of those nations, married and interwoven together, and occasionally crossed with a slight dash of the Indian."</em></blockquote>

Stereotypes notwithstanding, Irving was correct in anticipating that the culture emerging in Little Rock would soon eclipse that of the Post. Creole ways could not long endure the steady influx of settlers and institutions from the East. What, indeed, would become of the world of Creole Arkansas—and of those who called it home?

The outcomes were mixed. Compared to Creole communities in cities like St. Louis and New Orleans, French-speakers in Arkansas generally fared worse (Gitlin 2010). Even in those larger cities, the principal beneficiaries of U.S. expansion were individuals who were well-connected, politically savvy, and aligned with bourgeois sensibilities—those who held both capital and influence. In Arkansas, such families were already scarce and quickly outnumbered following the arrival of the Republic. Even those who qualified for citizenship often found themselves politically marginalized. Nevertheless, they turned to other strategies for survival.

Some Arkansas Creoles made modest fortunes by tapping into Anglophone business networks, sometimes through marriage into the families of Protestant newcomers—much to the dismay of parish priests at Arkansas Post (Woods 1989). Indeed, in the older-settled southeastern part of the territory, it was a common strategy of cultural and financial survival for daughters of Creole families to marry English-speaking newcomers (especially if they were Catholic), but the reverse was much rarer. François Lefevre, however, did just that. A resident of the Little Rock area and member of a well-known family of Canadian settlers who had become farmers and traders at Arkansas Post before relocating upriver to the new territorial capital in 1821, he married Polly Jones in the city and went on to become an important businessman in the growing frontier town.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/fcm8HArcQS3FFpBp95-z_.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption>Cunningham, M. Marriage certificate by justice of the peace certifying that François [Godefroy] Le Fevre and Polly Jones were married by him on October 5, 1821, 1821, collection of Historic Arkansas Museum, Gift of Mr. and Mrs. A. Howard Stebbins III, 92.036.</figcaption>
</figure>

Some property-owning Creoles sought to retain control of their land through various negotiation strategies—some successful, others not—with the U.S. government. These efforts included claiming rights to concessions granted under the Spanish regime, asserting Indigenous ancestry to qualify for land set aside for the Quapaw Nation, and appealing to the U.S. Congress to honor those claims.

Others, as we will see—compelled by kinship ties, opportunity, or sheer necessity—followed the shifting boundaries of the American nation. Some first resettled among the Caddo in northwestern Louisiana before eventually moving to a small portion of what is now Oklahoma.

Enslaved Arkansas Creoles pursued survival strategies of their own. While the institution of slavery continued to expand during the American period, a few individuals who had been enslaved in the world of Creole Arkansas—such as Marie Jeanne of New Orleans and Arkansas Post—were able to secure their freedom through the old Spanish-colonial institution of self-purchase and build lives of dignity and relative prosperity as business owners under the new regime.

French continued to be used in Arkansas much as it always had—through spoken language and epistolary correspondence (Vaugine de Nuisement 2005. Unlike New Orleans, however, Arkansas lacked an established print culture prior to the American regime, and local institutions did little to support one. Outsiders often assumed that Arkansas Creoles were illiterate or unenterprising—newspapers, one observer claimed, were “almost unknown” to them. Yet evidence suggests otherwise: some families, such as the Villemonts, subscribed to William Woodruff’s <em>Arkansas Gazette</em>, the first newspaper in the territory. Still, the paper did not cater to its French-speaking readership, offering only a single political advertisement in French. To sustain their language and cultural expression, French speakers in Arkansas had to rely on connections to others in the broader Creole Corridor and on a few Francophone newcomers who arrived during the early American period.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/_pfb-vmCKeDq92JicvxwT.png" alt="" loading="lazy" decoding="async">
  <figcaption>This announcement of a candidate for the House of Representatives of the Arkansas Territory was printed in both English and  French, ostensibly for the benefit of Arkansas Creoles. It is, in fact, the only excerpt the <em>Gazette </em>ever printed in  French. <em>The Arkansas Gazette</em>. April 29, 1820, p. 3. Arkansas Post, Arkansas. Source: Newspapers.com.</figcaption>
</figure>

New French-speaking migrants—some arriving by circuitous routes shaped by the upheavals of the French and Haitian revolutions—helped build upon the Creole culture they encountered in Arkansas. This group included clergy as well as individuals like Notrèbe and Barraqué, who quickly became prominent figures within the Creole community. They earned the trust of both longtime settlers and their Quapaw neighbors, often serving as intermediaries with the new American regime. Families such as the Vaugines of eastern Arkansas continued to send their children to school in New Orleans and maintained correspondence with relatives in Europe, writing in French well into the nineteenth century.

In the end, Arkansas Creoles were unable to sustain many of these cultural practices over the long term. Yet the range of strategies they employed—educational, diplomatic, entrepreneurial—reveals their remarkable adaptability in navigating, and at times flourishing within, a rapidly transforming world. One statistic is particularly revealing: less than a decade after Arkansas achieved statehood in 1836, Catholics made up fewer than 1% of the state’s population (Woods 1989).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/51b287ae-6bd8-41fd-8fcb-b1ce35ac6bd5.jpeg" alt="" loading="lazy" decoding="async">
  <figcaption><em><strong>Image:</strong></em><em> Ouachita River near Moro Bay State Park, Bradley County, Arkansas. Moro Bayou likely derives its name from the French surname Moreau (author’s photo). The term bayou—borrowed into American English through Louisiana French is thought to originate from the Choctaw </em>bayuk<em>, meaning “small stream.” Its use is especially widespread in placenames in present-day Louisiana and Arkansas (Wikipedia, “Bayou,” </em><a href="https://en.wikipedia.org/wiki/Bayou"><em>https://en.wikipedia.org/wiki/Bayou</em></a><em>).</em></figcaption>
</figure>

<a id="mapping-survival-strategies"></a>
### Spanish Land Grants

The Spanish land grant system was nominally honored by the U.S. government. If an individual could prove both that they had received the land through an official Spanish document and that the property had been occupied and “improved,” their claim would be recognized. U.S. surveys of these Spanish land grants became a tool for supporting Creole land claims—especially amid the growing influx of American squatters and the government’s negotiations with the Quapaw and other tribes to “officially” annex land in Arkansas.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/4gWAAVSI-L8uSVYnUE1ng.png" alt="" loading="lazy" decoding="async">
  <figcaption>1819 US Survey of "Spanish Land Grant" Accorded to Pedro (Pierre) Pertuis. (Source: <a href="http://www.cosl.org">Arkansas Commissioner of State Lands</a>)</figcaption>
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/20SEH6hD93qdd_nkYIgwX.png" alt="" loading="lazy" decoding="async">
  <figcaption>Satellite imagery of the same area</figcaption>
</figure>

<a id="lines-of-dispossession-us-quapaw-treaties"></a>
### Lines of Quapaw Dispossession

Signed at St. Louis on August 24, 1818, the treaty later designated “Cession 94” formalized the removal of the Quapaw from most of their ancestral lands. The vast "ceded" area is highlighted on this map. In return, the Quapaw retained only a narrow wedge of land—bounded by Arkansas Post to the east and Little Rock to the west—entirely south of the river and hemmed in by white settlements. U.S. negotiators described this as a permanent "reservation" under U.S. protection...

<figure class="interactive-map">
  <iframe src="maps/quapaw-treaty-map.html"
          title="Interactive map of Quapaw treaty lands and territorial change, 1818–1833"
          loading="lazy"
          allowfullscreen></iframe>
  <figcaption>Interactive map of Quapaw territorial dispossession and relocation, 1818–1833. Use the date buttons to move among the 1818 and 1824 cessions and the land assigned to the Quapaw in 1833; optional layers provide Native Land Digital territorial representations and modern state boundaries.</figcaption>
</figure>

...But little more than five years after signing the Treaty of 1818, the United States took even that. On November 15, 1824, under a new treaty (“Cession 121”), the Quapaw were pressured into ceding all claims in Arkansas, retaining only an 80-acre parcel at Saracen’s village. They agreed to relocate to Caddo lands near the Red River by early 1826 — a move that proved disastrous and prompted many to return within a year.

<a id="a-creole-carve-out"></a>
### A Mixed-Ancestry Carve-Out

The seventh article of the 1824 treaty between the United States and the Quapaw Nation featured a unique provision: it allocated land—or confirmed existing land claims—along the Arkansas River, within what had been the Quapaw reserve since 1818, to eleven parties. The justification? The individuals named—all Arkansas Creoles with French surnames—were described as “Indians by descent.” This designation enabled them to remain amid the forced removal of the Quapaw and the anticipated influx of Anglo-American settlers.

<p style="text-align: center;"><strong>The individuals named in the treaty are:</strong></p>

<div style="max-width: 820px; margin: 1.5rem auto 2.5rem;">
<table style="width: 100%; margin: 0 auto; border-collapse: collapse;">
  <thead>
    <tr>
      <th style="width: 6%; text-align: center;">#</th>
      <th style="width: 28%; text-align: center;">Individual</th>
      <th style="text-align: left;">Article 7 provision</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">1</td>
      <td style="text-align: center;"><strong>Francois Imbeau</strong></td>
      <td>Granted the starting tract on the south side of the Arkansas River near Little Rock, opposite “Wright Daniel’s farm,” just east of the “Quapaw Line” that ran through the town.</td>
    </tr>
    <tr>
      <td style="text-align: center;">2</td>
      <td style="text-align: center;"><strong>Joseph Duchassin</strong></td>
      <td>Received the next tract of land downriver.</td>
    </tr>
    <tr>
      <td style="text-align: center;">3</td>
      <td style="text-align: center;"><strong>Saracen [Sarassin]</strong></td>
      <td>Identified explicitly as a “half-breed Quapaw,” Saracen received eighty acres including his existing residence opposite Vaugine’s. He is the only person in this list who also appears among the treaty’s Quapaw signatories.</td>
    </tr>
    <tr>
      <td style="text-align: center;">4</td>
      <td style="text-align: center;"><strong>Batiste Socié</strong></td>
      <td>Eighty acres adjoining Saracen’s grant.</td>
    </tr>
    <tr>
      <td style="text-align: center;">5</td>
      <td style="text-align: center;"><strong>Joseph Bonne</strong></td>
      <td>Eighty acres adjoining Socié’s grant.</td>
    </tr>
    <tr>
      <td style="text-align: center;">6</td>
      <td style="text-align: center;"><strong>Baptiste Bonne</strong></td>
      <td>Eighty acres adjoining Joseph Bonne’s grant.</td>
    </tr>
    <tr>
      <td style="text-align: center;">7</td>
      <td style="text-align: center;"><strong>Lewis Bartelmi [Louis Barthélémi]</strong></td>
      <td>Eighty acres adjoining Baptiste Bonne’s grant.</td>
    </tr>
    <tr>
      <td style="text-align: center;">8</td>
      <td style="text-align: center;"><strong>Antoine Duchassin</strong></td>
      <td>Eighty acres adjoining Bartelmi’s grant.</td>
    </tr>
    <tr>
      <td style="text-align: center;">9</td>
      <td style="text-align: center;"><strong>Baptiste Imbeau</strong></td>
      <td>Eighty acres adjoining Antoine Duchassin’s grant.</td>
    </tr>
    <tr>
      <td style="text-align: center;">10</td>
      <td style="text-align: center;"><strong>Francois Coussot</strong></td>
      <td>Eighty acres adjoining Baptiste Imbeau’s grant.</td>
    </tr>
    <tr>
      <td style="text-align: center;">11</td>
      <td style="text-align: center;"><strong>Joseph Valliere</strong></td>
      <td>Eighty acres adjoining Francois Coussot’s grant.</td>
    </tr>
  </tbody>
</table>
</div>

Although the treaty singled out “Indians by descent,” some of the men it named were themselves of exclusively European ancestry and were apparently included because they had wives of Indigenous ancestry. Moreover, with the exceptions of Saracen and the Bonnes, the Indigenous connections of those singled out in the treaty were generally not Quapaw but tied to other Native nations—a striking fact given that the treaty was ostensibly an agreement with the Quapaw Nation specifically. An “Indian by descent”—or, in another term used in the treaty, a “half-breed”—occupied a category somewhere between Indian and white. U.S. officials thus implicitly positioned these Creoles “in between” Indigenous and American nations, highlighting their perceived difference both from English-speaking settlers and from more recent French arrivals, including the U.S. negotiators of this very treaty, who may have shared some of these prejudices.

The logic behind these allocations anticipated what would later become U.S. “blood quantum” policy: a bureaucratic framework that treated Indianness as inheritable, quantifiable, and subject to state recognition.

The "carve-out" for local Creoles was brokered by French-speaking newcomers from France, such as Frederick Notrebe and Antoine Barraqué, who had arrived in Arkansas by way of the French and Haitian Revolutions. As key intermediaries between local Creole families and the U.S. government, they may also have played on American stereotypes to secure this momentary reprieve for older French-speaking settlers before the coming torrent of Anglo-American settlers.

Those familiar with Southeast Arkansas will recognize some of these names. They still appear on maps and markers in territory that was once Quapaw land, designated as Cession 121 in the 1824 Treaty.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/dAfaJsBsYS9apT44S9UWq.png" alt="" loading="lazy" decoding="async">
  <figcaption><strong>Above</strong>: Detail from an original copy of the 1824 Treaty between the Quapaw and the US Government, with partial list of signatories and portion indicating the grants from the land being seized to be awarded to several Arkansas Creoles "being Indians by descent," including Barthelemy (Louis), Bonne (Joseph and Baptiste), Coussot (François), Duchassin (Joseph and Antoine), Imbeau (François and Baptiste), Saracen, and Saucier (Baptiste).</figcaption>
</figure>

<a id="joining-indian-removal-arkansass-m-tis-creoles-and-the-treaty-of-1833"></a>
### Joining Indian Removal

<blockquote><em>“The United States hereby agree to convey to the Quapaw Indians the hundred and fifty sections of land west of the State line of Missouri and between the lands of the Senecas and Shawnees, not heretofore assigned to any other tribe of Indians… expressly designed to be in lieu of their location on Red River and to carry into effect the Treaty of 1824, in order to provide a permanent home for their nation.” </em></blockquote>

— Indian Treaty 186, New Gascony, Arkansas Territory, May 13, 1833

A third treaty—the Treaty of 1833, signed in New Gascony, Arkansas, between the United States and the Quapaw Nation—marked the tribe’s forced removal from Arkansas to Indian Territory, concluding a long process of dispossession. Under its terms, the U.S. government granted the Quapaw a small tract of land in what is now northeastern Oklahoma.

Several Creole adoptees—some granted land in the 1824 Treaty—appear to have accompanied the Quapaw to the Red River and, in some cases, on to Oklahoma. Surnames such as Imbeau, Vallière, Coussot, and Desruisseaux (namesake of another bayou in Cession 121) appear on Quapaw rolls from Oklahoma in 1890. Historian Sonia Toudji notes that Quapaw patrilineal traditions did not prevent the naturalization of men with French forefathers, especially in times of crisis and displacement (Toudji 2011b).

By the 1880s, the Quapaw Nation, having suffered multiple rounds of removal by the U.S. government that split its population into different bands, faced a population crisis among the home band living in Oklahoma. Officially, their numbers had decreased to only forty people. The U.S. government was pushing the Quapaw to cede their sovereignty and incorporate into the Osage Tribe. Determined to retain their identity, Quapaw leaders dispatched a delegate to the Pine Bluff, Arkansas area with the mission of convincing residents they called “Arkansas Quapaws” to settle alongside them on the Quapaw reservation. That representative was none other than Alphonsus Vallier, a relative of Joseph Vallière, commandant of Arkansas Post under Spanish rule. He persuaded members of the Dardenne, Imbeau, and Desruisseaux families, among others, to return with him to Oklahoma, thus reinforcing the home band and ensuring the independence of the nation (Arnold 2016, 296). The Quapaw Nation remains a U.S. federally recognized tribe today, with more than 6,000 enrolled citizens.

<a id="the-villemonts-of-chicot-county"></a>
### The Villemonts of Chicot County

Near a bend in the Mississippi River—locally known by Creoles as the “Point of Stumps” (Pointe aux Chicots), a warning of submerged navigation hazards—the descendants of a commandant of Spanish Arkansas established a plantation on a vast tract of land. The Villemont family, led by Charles de Villemont, eventually lost their claim to this land following a legal dispute with the United States government. Despite this setback, the Villemonts and their descendants remained in Arkansas, maintaining ties with relatives in Louisiana and France through letters they composed in French.

The town of Villemont, named after the former commandant, was once a thriving port and served as the first capital of Chicot County, established in 1823. Situated along the banks of the Mississippi River, the town was ultimately swept away by flooding in 1847.

A decade earlier, the Villemont heirs had appealed to the U.S. Congress to reaffirm their family’s claim to land that had since been overtaken by English-speaking squatters. Their petition was met with objections from the new settlers—specifically Walworth and Miles—and was ultimately dismissed. One of the key reasons cited was that the Villemont family had not continuously occupied or “improved” (i.e., developed) the land, a requirement under U.S. land policy. When the matter later reached the courts, the ruling went even further: under the original 1795 Spanish concession, Don Carlos de Vilemont had been obligated to build a road, clear the front of the land, and establish a settlement within three years—conditions he never fulfilled. Because no improvements were made before the 1803 U.S. cutoff for validating foreign grants, and because the tract could not be reliably located or surveyed, the Supreme Court concluded in 1851 that neither the Spanish authorities nor the United States had ever been bound to recognize the claim.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/JPv2g2KAdwgSs-J0jH8n4.jpg" alt="" loading="lazy" decoding="async">
  <figcaption>The French naturalist Charles-Alexandre Lesueur passed this spot in 1829 and produced this view of “the Villemont habitation at Pointe Chicault.” The drawing shows a house that appears to be built in the Creole vertical-log construction style, surrounded by a fence, piles of wood, cattle grazing, and felled trees. If the Villemonts had not developed the land before the Louisiana Purchase, they had clearly begun to do so by this time. A nearby stand of trees is labeled “poplars” (likely cottonwoods). Pencil on paper, 7 × 9¾ in. Courtesy of the Muséum d’Histoire Naturelle, Le Havre, France. Adjusted (contrast increased) for clarity.</figcaption>
</figure>

Disputes over land claims like these may also reflect underlying prejudice against Creoles. In 1819, British naturalist Thomas Nuttall visited Arkansas and expressed surprise that many French-speaking property owners seemed uninterested in transforming their farms into profitable ventures. He observed that their practices were largely "opposed to improvement," noting with disapproval the absence of even "a kitchen garden” among these “Canadian descendants.” In his view, prolonged exposure to Indigenous cultures had detached them from the comforts and industrious habits of so-called civilized life. Nuttall predicted that such communities would inevitably be overtaken by more ambitious settlers from the East, suggesting that “progress” required the displacement of Arkansas’s less industrious inhabitants.

During his time in Pine Bluff, Nuttall offered a particularly critical account of his host, "Mons. Bartholome"—likely Joseph Barthélémy, of the clan that lent its name to Bayou Bartholomew—and several neighboring families. He described them as living more like hunters than farmers, likening their way of life to that of Indigenous peoples and criticizing them for paying little attention to cultivating the land.

In Chicot County, French families such as the Vaugines, Bogys, and Villemonts intermarried with English-speaking settlers arriving from the East. In many cases, however, they maintained their Catholic cultural identity—for example, the Villemonts sent their daughter to the school run by the Sisters of Loretto. In this rapidly changing region, enslaved labor and riverfront land were among the most valuable assets. As a result, intermarriages between English-speaking arrivistes and the established Francophone elite were often economically advantageous for both parties.

<a id="northeast-arkansas"></a>
### Northeast Arkansas

In the northeastern part of what is now Arkansas, French-speaking communities emerged along the White, Black, and St. Francis rivers.

The Janis family was a cornerstone of this community. Originally migrating from Quebec and Montreal, the patriarch, Nicholas Janis, was a captain of the militia in Kaskaskia (Illinois) and later a judge. He established a considerable household with a large retinue of enslaved servants. Following the American Revolution and the 1787 Northwest Ordinance (which banned slavery), many Creoles on the east side of the Mississippi migrated to the Spanish-controlled west bank.  While Nicholas moved to Ste. Genevieve around 1788, his son (or relative) Antoine Janis led an expansion further south into the Arkansas Ozarks, appearing as a hunter on the White River as early as 1781<br/><br/>Antoine Janis and his son Nicholas (also known as Antoine) secured significant Spanish land grants on the Black River. Joseph Janis, another son, was one of five French-speaking settlers who originally held the land that became the American town of Davidsonville. Victoria Janis married Pierre LeMieux, who established the primary French settlement at Clover Bend<br/><br/>Perhaps the most celebrated member of the family was Jean Baptiste Janis, who had fought against the British in the War of American Independence, serving as an ensign under George Rogers Clark at the 1779 Battle of Vincennes. <br/><br/>Despite that record of service, the transition to American rule after the 1803 Louisiana Purchase was difficult for the Janis family. Jean Baptiste Janis ultimately lost an 8,000-arpent Spanish land grant because he could not speak English and was unaware of the new American laws requiring the registration of land titles. In his final years, impoverished and "oppressed with age and infirmity," he successfully petitioned Congress for a Revolutionary War pension of $10 per month, which was approved just months before his death in 1836 (Lankford 1995; Kurlandski 2025).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/QKnqLBJM0YBupPrQjZQi-.jpg" alt="" loading="lazy" decoding="async">
  <figcaption>Commission for a Militia Post at Ste. Geneviève Granted to Jean-Baptiste Janis by the Baron de Carondelet. (Carondelet to "Janniss," Huntington Library Manuscrupts, HM 34002). Although somewhat popular among Creoles because he spoke French as his mother tongue, the Spanish governor of Louisiana, Carondelet was not without his detractors. In the 1790s, several Creole citizens from a variety of racial backgrounds, were arrested for singing a song mocking Carondelet as "cochon de lait," meaning suckling pig (Tsien 2023).</figcaption>
</figure>

<a id="st-marys-church-anchor-of-a-community"></a>
### St. Mary’s Church: Anchor of a Community

By all accounts, St. Mary’s is the oldest standing Catholic church structure in Arkansas. Its first iteration was a long structure built on land donated on July 4, 1837, by Creed Taylor “to Bishop Rosati [of St. Louis] for the use of the Catholics of Jefferson County” (Fitzgerald 1892). The timbers for the church, which measured 20 by 40 feet, were milled at Taylor’s own water-powered sawmill. Taylor also built a schoolhouse and gave several existing cabins, likely former slave quarters, for the use of the Sisters of Loretto, who had been invited from Kentucky by the prominent men of the area to teach their daughters and sons. St. Mary’s predecessors in the region, no longer standing, included a small chapel at New Gascony (St. Peter’s, at Barraque’s Landing) and another at Arkansas Post, built during the Spanish colonial period and dedicated to St. Stephen (Bearss and Brown 1971, 39).

One of the few priests to serve that chapel was an émigré from the French Revolution who had been welcomed to the United States by John Carroll, the nation’s first bishop, appointed in 1789. Carroll—a member of a prominent Maryland Catholic family whose cousin was the only Catholic signer of the Declaration of Independence—worked closely with the War Department to expand American influence in Indian territories, leveraging what they reasoned was the longstanding authority of Catholic clergy. His missionaries were tasked not only with tending to the spiritual needs of French-speaking Catholics but also with advancing diplomatic relations with both French and Indigenous communities across the Midwest.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/yTY5_9JSdQXTABXZXxslw.png" alt="Black-and-white photo of an historic cemetery with gravestones surrounding a small church." loading="lazy" decoding="async">
  <figcaption>St. Mary's Church, Plum Bayou, Jefferson County, Ark. photo 8/17/1972. Mother Agnes Hart on marker on this photo. Loretto Community Heritage Center Archives.</figcaption>
</figure>

Two such missionaries, including Pierre Janin, were promised annual congressional stipends of two hundred dollars for their service. When the funding failed to materialize—and disheartened by what he perceived as a lack of piety among his assigned parishioners—Janin left his post in Kaskaskia, Illinois. He instead accepted a position across the Mississippi, on the Spanish-controlled side, at Arkansas Post, where he ministered at St. Mary’s Church from 1796 to 1799 (Marvin 2015; Villerbu 2016).

A letter from a confrere—and fellow French émigré—foretold Janin’s departure and served as a warning to Bishop Carroll, and by extension, to the U.S. government. Writing from Prairie du Rocher in early 1796, Gabriel Richard, pastor of the Catholic parish at Detroit, explained that Janin’s defection to the Spanish side was all but inevitable:

<blockquote><em>“Father Janin...might well accept a position on the Spanish side... [He] has yet to receive anything from Congress, which had promised him two hundred dollars... He thinks, by accepting support on the other shore [of the Mississippi], he is not failing either Congress or the inhabitants of Kaskaskia...” </em></blockquote>

— Letter from Gabriel Richard to Bishop John Carroll, Prairie du Rocher, 24 January 1796. Associated Archives of Saint Mary’s, 7B1.

Indeed, Father Janin absconded to Arkansas and immediately set to work reviving parish life in this long-neglected corner of the Spanish empire. He helped rebuild the old chapel in 1796 (Holweck 1919). He officiated a number of long-overdue marriages. Though fragmentary, the surviving records—seventeen bearing his signature between February 1797 and July 1802—are highly revealing. Alongside five additional entries recorded by his Irish successor, Father Juan (John) Brady, these marriage records offer an unparalleled glimpse into the social and cultural fabric of community life in Creole Arkansas.

Several patterns emerge from these early marriage records. First, they highlight the cohesion of the Francophone community across the Creole Corridor, even in the absence of regular clerical presence and despite the vast distances separating its settlements. While a small majority of individuals were born in Arkansas, many others came from downriver communities such as the Acadian and German Coasts of the lower Mississippi. Still others hailed from farther north, including Kaskaskia (Illinois), Vincennes (Indiana), Detroit (Michigan), and even Montreal and Quebec City. Some had roots well beyond the Creole Corridor—among them English-speaking Catholics from Virginia and North Carolina, as well as Spanish-speakers from New Mexico and Spain.

After the last priest under Spanish patronage departed, the area was almost completely devoid of clergy for nearly a generation. In 1824, with the territory soon to come under the jurisdiction of the new diocese at St. Louis, two Vincentian priests from France traveled southwest from Missouri to visit French and Quapaw settlements long without missionaries. Several devastating floods of the Arkansas River—one of which destroyed the church of St. Stephen in the old fort—had already pushed settlers upriver from the Post. Journeying from Little Rock and down to the Post, Fathers John Timon and Jean-Marie Odin found Creole elders reciting prayers from memory and “strongly attached” to the "name of Catholic." When asked about Methodist preachers who had been active in the area they repeated that they would never embrace what they called "the American religion."   The younger generations, however, were more curious, and where for a long time they had been “rather exact not to contract any alliance” with Protestants, such marriages were becoming more common.

The reestablishment of a Catholic presence in Arkansas was slow but steady under Bishop Rosati of St. Louis. St. Mary’s Church became an early focal point of this revival, serving both settlers and members of the Quapaw Nation. Some Quapaw worshipers may have prayed here, and local tradition holds that the church’s crucifix was carved by Saracen, a prominent tribal leader whose name appears on all nineteenth-century treaties between the Quapaw and the U.S. government. The son of a Quapaw woman and a French interpreter, Saracen (or Sarassin) rose to prominence as a spokesperson for his people and was a devout Catholic. He was later reinterred in the cemetery at St. Joseph’s Church in Pine Bluff. St. Mary’s also became the spiritual home of Sister Agnes Hart, who led the Sisters of Loretto from Kentucky to Arkansas to establish a Catholic school and whose grave was also moved to the site in the 1860s (Owens 1961).

St. Mary’s Church owes its survival, in part, to the preservation efforts of Emma Vaugine White in the 1920s. An heiress from one of Creole Arkansas’s most prominent families, she remained deeply connected to her French heritage. White rallied community support and secured financial backing for conservation of the site, including through organizations such as the Daughters of the American Revolution. Her ancestor, Francis Vaugine—who served in the American War of Independence—is buried at the church. Framing her family’s legacy within the broader narrative of U.S. history may well have been key to winning the support needed for her preservation work. Today, thanks to the efforts of Father Joseph Marconi, pastor of St. Joseph’s Parish in Pine Bluff, the church has undergone new restoration and once again hosts monthly Mass for its devoted parishioners.

Today, the church and its cemetery stand as a powerful testament to Creole Arkansas—guardians of traditions and family histories amid the sweeping demographic and political changes of the nineteenth century.

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/Pn09vzh7BQCFHRq8t9B3z.jpeg" alt="Interior of a chapel with white pews and a car visible through the open door at the end." loading="lazy" decoding="async">
  <figcaption>Interior of St. Mary's Church. Photo 2023. <a href="https://www.stjosephpinebluff.org/st-mary-catholic-church.html"> https://www.stjosephpinebluff.org/st-mary-catholic-church.html </a></figcaption>
</figure>

<figure>
  <a href="https://www.arkansas-catholic.org/news/article/7973/Mass-resumes-at-oldest-Catholic-church-after-repairs" target="_blank" rel="noopener"><img src="https://www.arkansas-catholic.org/photos/7973/0909-plum-bayou-2.jpg" alt="" loading="lazy" decoding="async"></a>
  <figcaption><a href="https://www.arkansas-catholic.org/news/article/7973/Mass-resumes-at-oldest-Catholic-church-after-repairs" target="_blank" rel="noopener">Mass resumes at oldest Catholic church after repairs - Arkansas Catholic - September 8, 2023</a> — While the community of Plum Bayou is redefining its future, it is cherishing its past. Until recently, St. Mary Church sat with nothing but a collection of headstones to keep it company. That is, until Father Joseph Marconi decided that it was time for a fresh start.</figcaption>
</figure>

<a id="baptisms-and-burials"></a>
### Baptisms and Burials

According to local tradition, the origins of St. Mary’s reach back to a chapel said to have been built on a barge at Arkansas Post in the 1780s and later floated upriver. Whatever the truth of that story (were portions of an older structure perhaps incorporated into one of the first churches built above the Post?), the first securely documented reference to church construction appears to be from the early American period. After 1824, Father John Martin “established a home and chapel” above the Post in one of the upriver establishments, and in early 1832 Father Pierre Beauprez opened a “log mission” below Pine Bluff. His successor, Father Ennemond Dupuy, made his residence there and in January 1833 arranged the purchase of ten arpents from the Vaugine family, three miles below Pine Bluff, at a cemetery blessed some eight years earlier by Father Odin. By that time Dupuy had already “commenced constructing a building” near the site; in an 1837 letter to Bishop Rosati he described “the chapel and the priest’s house which I built” on the left bank of the Arkansas, at a bend known as Sainte-Marie. The Vaugines would remain the principal benefactors of the church, its cemetery, and the short-lived academy hosted at the site for generations.

Earlier parish histories and diocesan summaries usually date the move of St. Mary’s to its present location at Plum Bayou to 1869, attributing it to persistent flooding along the river. Historian of St. Joseph’s Parish in Pine Bluff (of which St. Mary’s remains a mission parish), Eleanor Lambert, places the move sometime between 1839 and 1851—a range that fits the evidence: on 27 July 1851, at least five baptisms were recorded at “St. Mary’s, Plum Bayou,” and on 6 May 1851 John and Emily Foley deeded the Plum Bayou site to the bishop of Arkansas for one dollar. The new site, along Plum Bayou, lay on higher, less flood-prone ground and formed part of a vital corridor between the Arkansas River near the Post and the farmlands of the Grande Prairie north of present-day Little Rock. Many of the remains from the cemetery—at least those not already claimed by the river—were exhumed and reinterred there.

Photos from 1920 show a substantially different church building from the one pictured in the oldest known photograph of St. Mary’s (at either site). It may be that the main structural elements were never wholesale rebuilt at the second site at all, but that an entirely new structure was erected there, perhaps integrating some of the old materials. In any case, in 1927 the frame structure at Plum Bayou was sheathed in brick and its interior ceiling altered—changes that later led the National Register of Historic Places to deny a 1974 listing on the grounds that the church no longer retained sufficient architectural integrity (Lambert 1985, 16–27).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/Zjd1-ZiduTEEp3MSQAb_q.png" alt="" loading="lazy" decoding="async">
  <figcaption>Photograph by S. A. Combs (Lites–Wallis Collection), dated 1869. It shows St. Mary’s Church, whether at its first or second location is unclear. A caption accompanying this same photograph elsewhere identifies the boy in the foreground as Ted Antoine. The women and children posing in front of the church may have been enslaved dependents of the Vaugine family. Captain Francis G. Vaugine (1832–1900), pictured on horsemark, was son of François (“Francis”) Nuisement Vaugine (1800–1846) and Odile (Audele) Desruisseaux, and great-grandson of Étienne Martin de Vaugine de Nuisement (1724–ca. 1794). He served in the Confederate army. Photo reproduced in Dave Wallis, “A Most Historic Church,” Jefferson County Historical Quarterly 3, no. 2 (1971): 14–19.</figcaption>
</figure>

Among the surnames inscribed on the grave markers at St. Mary's are Antwine (likely a variation of Antoine), Bogy, Coussot (rendered as Coosotte), Dardenne (Dardanne), Desruisseaux (Derreuisseaux), Vallières (Vallier), and, most prominently, Vaugine—all names that correspond to topographical features still visible on modern maps of Arkansas (Lambert 1985, 24–27). These individuals belonged to families with the means and social standing to secure religious burials, ensuring that their names would endure both in the landscape and in local memory.

The Register of St. Mary's Cemetery, first compiled by Father John Michael Lucey in 1877, also includes references to Missoria Folley, Teresa Bogy, and Elizabeth Vaugine, enslaved dependents of the families whose surnames they bore. Records of enslaved people also appear in the few surviving baptismal registers from St. Mary’s (Arkansas State Archives, VF 1526). Indeed, enslaved and free people of color made up a significant proportion of the Catholic faithful in Arkansas. A rudimentary 1820 census compiled by Father Martin records 3 Black Catholics in Fort Smith, 3 in Petit Rocher (Little Rock), 60 in Jefferson County, and 108 at Arkansas Post—about one-third of the total Catholic population of 522—a number that one of his successors, Father Saulnier, thought was closer to one thousand (Woods 1989, 227).

Most references to French-speaking Black Arkansans appear not in church records but in property inventories—a reminder of the ways enslaved people were denied autonomy and dignity. One of the most renowned Creole Arkansans of African descent—who may well have been a regular parishioner at St. Mary’s—was Marie Jeanne. Born around 1788 (she was listed as 62 years old in the 1850 census), she was originally recorded as the enslaved property of the prominent Vaugine family. She died in 1857 with a new name—“Mary John”—a free woman who had purchased her liberty from a later Anglophone owner. Sold for 800 piastres (dollars), she bought her freedom for the same amount on September 13, 1840. By the time of her death, Mary John was a well-known business owner in the region. Although the <em>Arkansas Gazette</em>’s obituary was filled with the era’s patronizing language, it nonetheless described her as “much respected” and renowned for her hospitality—especially her meals of coffee and venison steaks (Bohnert, 2023).

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/re77pMxFsDOTcN7-vQA-C.jpg" alt="A small cemetery with three gravestones surrounded by greenery and a chain-link fence." loading="lazy" decoding="async">
  <figcaption>Graves in St. Mary's Cemetery, Plum Bayou, Jefferson County, Ark. April 2025.</figcaption>
</figure>

<figure>
  <img src="https://www.arcgis.com/sharing/rest/content/items/ab8d60a903104d4ba8e2f21e60602b5d/resources/tEtwvmSgAXs_HUu7JpQhP.png" alt="" loading="lazy" decoding="async">
</figure>

[↑ Back to Contents](#contents)

<a id="references"></a>
## References

<a id="secondary-sources"></a>
### Secondary Sources

Allsopp, Fred W. <em>"Picturesque Nomenclature... An Exploration of How Some of the Peculiar Names of Arkansas Towns and Counties Originated."Arkansas Gazette</em>, July 18, 1937. <a href="https://www.geology.arkansas.gov/docs/pdf/publication/usgs_grants/written_media/miscellaneous_media/MiscMedia_PlaceNames.pdf">https://www.geology.arkansas.gov/docs/pdf/publication/usgs_grants/written_media/miscellaneous_media/MiscMedia_PlaceNames.pdf</a>.

Arnold, Morris S. <em>Unequal Laws unto a Savage Race: European Legal Traditions in Arkansas, 1686-1836</em>. Fayetteville: University of Arkansas Press, 1986.

———. <em>Colonial Arkansas, 1686-1804: A Social and Cultural History</em>. Fayetteville: University of Arkansas Press, 1993.

———. <em>The Rumble of a Distant Drum: The Quapaws and Old World Newcomers, 1673-1804</em>. Fayetteville: University of Arkansas Press, 2000.

———. “Eighteenth-Century Arkansas Illustrated.” <em>The Arkansas Historical Quarterly</em> 53, no. 2 (1994): 119. Accessed March 6, 2024.

———.  “Barthélémy Dit Charlot, a Colonial Arkansas Métis and Voyageur.” <em>The Arkansas Historical Quarterly</em> 74, no. 1 (2015): 1–17.

———. “François Ménard, a Colonial Arkansas ‘Marchand’ and ‘Habitant.’” <em>The Arkansas Historical Quarterly</em> 74, no. 4 (2015): 303–326.

———. “The Métis People of Eighteenth-and Nineteenth-Century Arkansas.” <em>Louisiana History: The Journal of the Louisiana Historical Association</em> 57, no. 3 (2016): 261–296.

———. “Colonial Arkansas Women.” <em>The Arkansas Historical Quarterly</em> 76, no. 1 (2017): 1–22.

———. <em> The Arkansas Post of Louisiana</em>. Fayetteville: University of Arkansas Press, 2017.

Babb, Winston Chandler. <em>French Refugees from Saint Domingue to the Southern United States, 1791-1810</em>. Charlottesville: University of Virginia, 1979.

Bandy, Everett. “Who Was Saracen?” Informational Paper. Quapaw Nation (Oklahoma), n.d. Accessed August 3, 2025. https://www.quapawtribe.com/598/Saracen.

———. <em> </em>“O-Ga-Xpa Ma-Zho<sup>n</sup>: Quapaw Country.” Informational Paper. Quapaw Nation (Oklahoma), 2020. <a href="https://www.quapawtribe.com/DocumentCenter/View/9804/Quapaw-Country">https://www.quapawtribe.com/DocumentCenter/View/9804/Quapaw-Country</a>.

Bearss, Edwin C, and Lenard E Brown. <em>Arkansas Post National Memorial: Structural History[,] Post of Arkansas, 1804-1863 and Civil War Troop Movement Maps[,] January, 1863</em>. National Parks Service: Washington, D.C., April 1971.

Beaupré, Andrew R. “The Posts along the Arkansas: A Brief Introduction to French Settlement in the Arkansas River Valley.” <em>Le Journal: The Center for French Colonial Studies</em> 40, no. 1 (2024): 4–12.

Blaetz, Robin. <em>Visions of the Maid: Joan of Arc in American Film and Culture</em>. Cultural Frames, Framing Culture. Charlottesville: University Press of Virginia, 2001.

Blaufarb, Rafe. <em>Bonapartists in the Borderlands: French Exiles and Refugees on the Gulf Coast, 1815-1835</em>. Reprint Edition. University of Alabama Press, 2016.

Bohnert, Dyan. “Mary John (?-1857).” In <em>Encyclopedia of Arkansas</em>. Little Rock, Arkansas: Central Arkansas Library System, 2023. <a href="https://encyclopediaofarkansas.net/entries/mary-john-4367">https://encyclopediaofarkansas.net/entries/mary-john-4367</a>.

Branner, John C. “Some Old French Place Names in the State of Arkansas.” <em>The Arkansas Historical Quarterly</em> 19, no. 3 (1899) 1960: 191–206.

Buck, Kate. “Big Rock.” <em>Encyclopedia of Arkansas</em>. Central Arkansas Library System. Last updated January 29, 2024. Accessed August 29, 2025. <a href="https://encyclopediaofarkansas.net/entries/big-rock-5492/">https://encyclopediaofarkansas.net/entries/big-rock-5492/</a>

Burton, Helen Sophie, and F. Todd Smith. <em>Colonial Natchitoches: A Creole Community on the Louisiana-Texas Frontier</em>. Texas A&amp;M University Press, 2008.

Catton, Theodore. <em>A Many-Storied Place: Historic Resource Study, Arkansas Post National Memorial, Arkansas</em>. Washington, D.C.: National Park Service, 2017. <a href="https://npshistory.com/publications/arpo/hrs.pdf">https://npshistory.com/publications/arpo/hrs.pdf</a>.

DeArmond-Huskey, Rebecca. <em>Bartholomew’s Song: A Bayou History</em>. Bowie, Maryland: Heritage Books, 2001

DeJean, Joan. <em>Mutinous Women: How French Convicts Became Founding Mothers of the Gulf Coast</em>. New York: Basic Books, 2022.

Deloria, Professor Philip J. <em>Playing Indian</em>. First Edition. New Haven: Yale University Press, 1998.

Dickinson, Samuel Dorris. “Colonial Arkansas Place Names.” <em>The Arkansas Historical Quarterly</em> 48, no. 2 (1989): 137–68.

Din, Gilbert C., and Abraham Phineas Nasatir. <em>The Imperial Osages: Spanish-Indian Diplomacy in the Mississippi Valley</em>. Norman: University of Oklahoma Press, 1983.

Dubuisson, Ann. “François Sarazin: Interpreter at Arkansas Post during the Chickasaw Wars.” <em>The Arkansas Historical Quarterly</em> 71, no. 3 (2012): 243–63.

DuVal, Kathleen. <em>The Native Ground: Indians and Colonists in the Heart of the Continent</em>. Philadelphia: University of Pennsylvania Press, 2007.

———. “Indian Intermarriage and Métissage in Colonial Louisiana.” <em>The William and Mary Quarterly</em> 65, no. 2 (2008): 267–304.

Edwards, Jay Dearborn, and Nicolas Kariouk Pecquet du Bellay de Verton. <em>A Creole Lexicon: Architecture, Landscape, People</em>. Baton Rouge: Louisiana State University Press, 2004.

Ekberg, Carl J., Abraham P. Nasatir, and Bernard K. Schram. <em>Colonial Ste. Genevieve: An Adventure on the Mississippi Frontier</em>. 2nd edition. Carbondale: Southern Illinois University Press, 2014.

Ekberg, Carl J., and Anton J. Pregaldin. “Marie Rouensa-8canic8e and the Foundations of French Illinois.” In <em>Native Women’s History in Eastern North America before 1900</em>, edited by Rebecca Kugel and Lucy Eldersveld Murphy, 203–33. Lincoln, Neb.: University of Nebraska Press, 2007.

Ellis, Elizabeth N. <em>The Great Power of Small Nations</em>. Philadelphia: University of Pennsylvania Press, 2023.

Evans, Tessa. "Adding Relief to Maps: French and Indigenous Cartography at the Arkansas Post." <em>H-France Salon, </em>Volume 16 (2024): 1.

Filhol, Emmanuel. “Bohémiens condamnés aux galères à l’époque du Roi-Soleil (1677 à 1715).” <em>Criminocorpus. Revue d’Histoire de la justice, des crimes et des peines</em>, June 2, 2020.

Jones, Linda C. “Nicolas Foucault and the Quapaws.” <em>The Arkansas Historical Quarterly</em> 75, no. 1 (2016): 4–26.

Fraser, Angus. <em>The Gypsies</em>. 2nd edition. Oxford, UK ; Cambridge, USA: Wiley-Blackwell, 1995.

García-Fernández, C., N. Font-Porterias, V. Kučinskas, E. Sukarova-Stefanovska, H. Pamjav, H. Makukh, B. Dobon, et al. “Sex-Biased Patterns Shaped the Genetic History of Roma.” <em>Scientific Reports</em> 10, no. 1 (September 2, 2020): 14464.

Gitlin, Jay. <em>The Bourgeois Frontier: French Towns, French Traders, and American Expansion</em>. New Haven: Yale University Press, 2010.

Gitlin, Jay, Robert Michael Morrissey, and Peter J. Kastor, eds. <em>French St. Louis: Landscape, Contexts, and Legacy</em>. Lincoln: University of Nebraska Press, 2021.

Gosnell, Jonathan K. <em>Franco-America in the Making: The Creole Nation Within</em>. Lincoln ; London: University of Nebraska Press, 2018.

Hall, Gwendolyn Midlo. <em>Africans in Colonial Louisiana: The Development of Afro-Creole Culture in the Eighteenth Century</em>. Baton Rouge: Louisiana State University Press, 1995.

Hancock, Ian F. <em>We Are the Romani People</em>. Hatfield: University of Hertfordshire Press, 2002.

Havard, Gilles, and Cécile Vidal. <em>Histoire de l’Amérique française</em>. Paris: Flammarion, 2008.

Havard, Gilles. <em>L’Amérique fantôme: Les aventuriers francophones du Nouveau Monde</em>. Paris: Flammarion, 2019.

Hayes, Derek. <em>Historical Atlas of the American West</em>. Berkeley: University of California Press, 2009.

Heerman, M. Scott. <em>The Alchemy of Slavery: Human Bondage and Emancipation in the Illinois Country, 1730-1865</em>. Philadeblphia: University of Pennsylvania Press, 2018.

Higgins, Donald. “Petit Jean Mountain.” <em>The Encyclopedia of Arkansas History and Culture</em>. Butler Center for Arkansas Studies. 2011. Last updated April 19, 2025. Accessed September 1, 2025. <a href="https://encyclopediaofarkansas.net/entries/petit-jean-mountain-6317/">https://encyclopediaofarkansas.net/entries/petit-jean-mountain-6317/</a>.

———.2019. “Point Remove Creek and the Cherokees, Part 2: The Point Remove Creek Landmark.” <em>Petit Jean Country Headlight</em> 142 (33) (October 16): 1–2.

Holweck, F. G. “The Arkansas Mission Under Rosati.” <em>St. Louis Catholic Historical Review</em> 1, no. 4–5 (October 1919): 243–67.

Hyde, Anne F. <em>Empires, Nations, and Families: A History of the North American West, 1800-1860</em>. Lincoln: University of Nebraska Press, 2011.

Jones, Kelly Houston. <em>A Weary Land: Slavery on the Ground in Arkansas</em>. Athens: University of Georgia Press, 2021.

Kirk, John A. <em>Winthrop Rockefeller: From New Yorker to Arkansawyer, 1912-1956</em>. Fayetteville: The University of Arkansas Press, 2022.

Kornhauser, Elizabeth Mankin, and Dorothy Mahon. “Technical Brilliance Revealed: Bingham’s Fur Traders Descending the Missouri.” In <em>Navigating the West: George Caleb Bingham &amp; The River</em>, 135–56. New Haven: Yale University Press, 2014.

Kurlandski, Jerry. “Jean Baptiste Janis, Pts. 1 and 2.” <em>Adventures in Genealogy</em>, September 20, 2025. <a href="https://www.genealogy.jkurlandski.com/aubuchon/jeanBaptisteJanis1.html">https://www.genealogy.jkurlandski.com/aubuchon/jeanBaptisteJanis1.html</a>.

Lambert, Eleanor R. <em>In the Palm of His Hand: The History of St. Joseph’s Catholic Church, Pine Bluff, Arkansas, 1838-1984</em>. Little Rock, Ark: August House, 1985.

Lankford, George E., and Jeannie Whayne. “Almost ‘Illinark’: The French Presence in Northeast Arkansas.” In <em>Cultural Encounters in the Early South: Indians and Europeans in Arkansas</em>, 88–111. Fayetteville: University of Arkansas Press, 1995.

Lawrence County Historical Society.<em> De Mun and Company: French Connections and the Founding of Lawrence County </em>(Research Presentation). Pocahontas, AR: Arkansas Historical Association / Lawrence County Historical Society, 2017.

Marrero, Karen L. <em>Detroit’s Hidden Channels: The Power of French-Indigenous Families in the Eighteenth Century</em>. Winnipeg: University of Manitoba Press, 2020.

Marvin, Nathan. “‘A Thousand Prejudices’: French Habitants and Catholic Missionaries in the Making of the Old Northwest, 1795-1805.” In <em>Une Amérique française, 1760-1860: dynamiques du corridor créole</em>, edited by Guillaume Teasdale and Tangi Villerbu, 113–40. Paris: Les Indes savantes, 2015.

Matache, Margareta. “Dear Gadjo (Non-Romani) Scholars….” <em>FXB Center for Health &amp; Human Rights | Harvard University</em> (blog), June 19, 2017. <a href="https://fxb.harvard.edu/2017/06/19/dear-gadje-non-romani-scholars/">https://fxb.harvard.edu/2017/06/19/dear-gadje-non-romani-scholars/</a>.

McDermott, John Francis. “The French in the Mississippi Valley.” In <em>St. Louis Families from the French West Indies</em>, edited by Dorothy Garesché Holland, 41–58. Urbana: University of Illinois Press, 1965.

McGrew, DeAnn. "Origins of the Legend of Petit Jean." Undergraduate thesis, University of Central Arkansas, December 10, 1999. UCA Archives &amp; Special Collections, SMC 1202.

McLeod, Walter E. “Early Lawrence County History.” <em>Arkansas Historical Quarterly</em> 3, no. 1 (Spring 1944): 37–52

Miles, Tiya. <em>The Dawn of Detroit: A Chronicle of Slavery and Freedom in the City of the Straits</em>. New York ; London: The New Press, 2017.

Mills, Elizabeth Shown. “Assimilation? Or Marginalization and Discrimination?: Romani Settlers of the Colonial Gulf (Christophe Clan).” Geneaological Resource. <em>Historic Pathways</em>, June 6, 2015. Accessed February 16, 2023. www.historicpathways.com.

Mills, Gary B., Elizabeth Shown Mills, and H. Sophie Burton. <em>The Forgotten People: Cane River’s Creoles of Color</em>. Revised edition edition. Baton Rouge: LSU Press, 2013

Milson, Andrew J. <em>Arkansas Travelers: Geographies of Exploration and Perception, 1804-1834</em>. Fayetteville: The University of Arkansas Press, 2019.

Morris, Robert Lee. “Ozark or Masserne.” <em>The Arkansas Historical Quarterly</em> 2, no. 1 (1943): 39–42.

Musco, Jonas, Paz Núñez-Regueiro, Everett Bandy, Ryan Spring, and Ian Thompson. “Back to the Sources. A Collaborative Research Project on the Indigenous Mississippi Valley and Southeast Based on 18th-Century French Maps (Musée Du Quai Branly-Jacques Chirac and the Choctaw, Miami, Peoria and Quapaw Nations).” <em>IdeAs. Idées d’Amériques</em>, no. 26 (October 2025). <a href="https://doi.org/10.4000/14v77">https://doi.org/10.4000/14v77</a>.

Núñez-Regueiro, Paz, Everett Bandy, George Ironstrack, Jonas Musco, Ian Thompson, and Céline Daher. 2025. “Matachées: Painted Hides, Indigenous Nations, and French Colonial Encounters along the Mississippi Valley.” <em>Gradhiva. Revue d’anthropologie et d’histoire des Arts</em>, no. 40 (November 2025). <a href="https://doi.org/10.4000/15620">https://doi.org/10.4000/15620</a>.

Ostendorf, Ann. “Louisiana Bohemians: Community, Race, and Empire.” <em>Early American Studies: An Interdisciplinary Journal</em> 19, no. 4 (2021): 659–98.

Owens, M. Lilliana. “Loretto Foundations in Louisiana and Arkansas.” <em>Louisiana History: The Journal of the Louisiana Historical Association</em> 2, no. 2 (1961): 202–29.

Ross, Margaret Smith. “Squatters Rights: Some Pulaski County Settlers Prior to 1814.” <em>Pulaski County Historical Review</em> 4, no. 2 (June 1956): 17–27.

———. “Pulaski County Tax List for 1828.” <em>Pulaski County Historical Review</em> 5 (1957): 42–48.

———. <em>Arkansas Gazette: The Early Years, 1819-1866; a History</em>. Little Rock: Arkansas Gazette Foundation, 1969.

Savoy, Lauret. <em>Trace: Memory, History, Race, and the American Landscape</em>. Berkeley, California: Counterpoint, 2015.

Schroeder, Walter. “Ozark Highlands.” In <em>The American Midwest : An Interpretive Encyclopedia</em>, edited by Richard Sisson, Christian Zacher, and Andrew Cayton. Indiana University Press, 2007.

———. <em>Opening the Ozarks: A Historical Geography of Missouri’s Ste. Genevieve District, 1760-1830</em>. First edition. University of Missouri, 2016.

Terrien, Yevan. “Baptiste and Marianne’s Balbásha’: Enslavement, Freedom, and Belonging in Early New Orleans, 1733–1748.” <em>Journal of American History</em> 110, no. 2 (September 1, 2023): 230–257.

Thompson, Laura Hinderks. “Historical Translation of Antoine Barraque Manuscript.” <em>The Arkansas Historical Quarterly</em> 40, no. 3 (1981): 220.

Toudji, Sonia. “Intimate Frontiers: Indians, French and Africans in the Mississippi Valley.” PhD Dissertation, Université du Maine – Le Mans, 2011.

———. “‘The Happiest Consequences’: Sexual Unions and Frontier Survival at Arkansas Post.” <em>The Arkansas Historical Quarterly</em> 70, no. 1 (2011): 45–56.

———. “Change and continuity: French and Indian alliance in the Mississippi Valley after the Treaty of 1763.” In <em>Une Amérique française, 1760-1860: dynamiques du corridor créole</em>, edited by Guillaume Teasdale and Tangi Villerbu, 205–228. Paris: Les Indes savantes, 2015.

Trouillot, Michel-Rolph. <em>Silencing the Past: Power and the Production of History</em>. Beacon Press, 1997.

Tsien, Jennifer. <em>Rumors of Revolution: Song, Sentiment, and Sedition in Colonial Louisiana</em>. Charlottesville: University of Virginia Press, 2023.

Usner, Daniel H. "Between Creoles and Yankees: The Discursive Representation of Colonial Louisiana in American History." In <em>French Colonial Louisiana and the Atlantic World</em>, edited by Bradley G. Bond, 1-22. Baton Rouge: Louisiana State University Press, 2005.

Vidal, Cécile. <em>Caribbean New Orleans: Empire, Race, and the Making of a Slave Society</em>. Chapel Hill: Omohundro Institute and University of North Carolina Press, 2019.

Villerbu, Tangi. “Structurer un territoire ecclésiastique : la géopolitique catholique entre Grands Lacs et Mississippi (1763-1803).” In <em>Vers un nouveau monde atlantique : Les traités de Paris, 1763-1783</em>, edited by Philippe Joutard, Didier Poton, and Laurent Veyssière, 211–19. Histoire. Rennes: Presses universitaires de Rennes, 2016.

Wegmann, Andrew N., and Robert Englebert, eds. <em>French Connections: Cultural Mobility in North America and the Atlantic World, 1600–1875</em>. Baton Rouge: Louisiana State University Press, 2020.

White, Richard. <em>The Middle Ground: Indians, Empires, and Republics in the Great Lakes Region, 1650-1815</em>. Anniversary edition. Cambridge: Cambridge University Press, 2010.

White, Sophie. <em>Wild Frenchmen and Frenchified Indians: Material Culture and Race in Colonial Louisiana</em>. Philadelphia: University of Pennsylvania Press, 2012.

Williams, Marion Imbeau. "Imbeau Family History." Typed history of descendants of Jean Baptiste Imbeau. University of Arkansas Libraries, Colonial Arkansas Post Ancestry, Core Family Papers (MC 1380, Box 58, File 1).

Woods, James M. “‘To the Suburb of Hell’: Catholic Missionaries in Arkansas, 1803-1843.” <em>The Arkansas Historical Quarterly</em> 48, no. 3 (1989): 217–42.

———. <em>Mission and Memory: A History of the Catholic Church in Arkansas</em>. Diocese of Little Rock, 1993.

Worthen, William B. "Little Rock (Geological Formation)." <em>Encyclopedia of Arkansas</em>. Updated September 2023. Accessed September 7, 2024. <a href="https://encyclopediaofarkansas.net/entries/little-rock-geological-formation-5251/">https://encyclopediaofarkansas.net/entries/little-rock-geological-formation-5251/</a>.

<a id="published-primary-sources"></a>
### Published Primary Sources

#### Correspondence

Lovely, William. [1813] 1949. “Notice of William Lovely to the Cherokee, July 20, 1813.” In <em>The Territorial Papers of the United States</em>, edited by Clarence Edwin Carter, 721. Vol. 14. Washington, DC: United States Government Printing Office.

#### Legal Documents

Arkansas Supreme Court,<em> Arkansas Reports</em> (State of Arkansas, 1858), 520.

Carondelet, Baron de to Jean-Baptiste Janis, Huntington Library Manuscripts, HM 34002.

#### Newspapers

Arkansas Gazette. 1819–1991. <em>Arkansas Gazette</em>. Arkansas Post, Little Rock, AR.

#### Textbooks &amp; Early Studies

Lucey, John Michael. “The Catholic Church in Arkansas.” In <em>Publications of the Arkansas Historical Association</em>, edited by John Hugh Reynolds, vol. 2. Fayetteville, AR, 1908.

Reynolds, John Hugh. Makers of Arkansas History. Stories of the States. New York: Silver, Burdett and Company, 1905.

Shinn, Josiah Hazen. <em>The History of Arkansas: A Text-book for Public Schools, High Schools, and Academies.</em> Little Rock: Wilson &amp; Webb Book &amp; Stationery Company, 1898.

#### Travel Writing

Berry, Trey, Pam Beasley, and Jeanne Clements, eds. <em>The Forgotten Expedition, 1804–1805: The Louisiana Purchase Journals of Dunbar and Hunter</em>. Reprint edition. LSU Press, 2014.

Irving, Washington. <em>The Crayon Papers</em>. 2005. <a href="https://www.gutenberg.org/ebooks/7994">https://www.gutenberg.org/ebooks/7994</a>.

Nuttall, Thomas. <em>A Journal of Travels into the Arkansas Territory</em>. The Newberry Library. Philadelphia : T. H. Palmer, 1821. <a href="http://archive.org/details/GR_3055">http://archive.org/details/GR_3055</a>.

Vaugine de Nuisement, Etienne. <em>Journal de Vaugine de Nuisement (ca 1765) : un témoignage sur la Louisiane du XVIIIe siècle.</em> Edited by Steve Canac-Marquis and Pierre Rézeau. Collection Langue française en Amérique du Nord. Presses de l’Université Laval, 2005.

<a id="archival-collections"></a>
### Archival Collections

#### Archdiocese of St. Louis

<li>Fitzgerald, Edmund. Bishop Edmund Fitzgerald to the Archdiocese of St. Louis, March 25, 1892. ADMN/C2/P/002297.</li>

#### American Philosophical Society

<li>George Izard, “31. Izard, George to the American Philosophical Society,” January 10, 1827, American Philosophical Society, American Indian Vocabulary Collection, Mss.497.V85, <a href="https://diglib.amphilsoc.org/islandora/object/text%3A310681">https://diglib.amphilsoc.org/islandora/object/text%3A310681</a></li><li>George Izard, “34. Vocabulary of the Quapaw Indians,” January 10, 1827, American Philosophical Society, American Indian Vocabulary Collection, Mss.497.V85,<a href="https://diglib.amphilsoc.org/islandora/object/34-vocabulary-quapaw-indians"> https://diglib.amphilsoc.org/islandora/object/34-vocabulary-quapaw-indians</a></li>

#### Archives nationales d’outre-mer (ANOM)

<li>Series C13A (French Louisiana)</li>

#### Arkansas State Archives

<li>Vertical File 1526, St. Mary’s Church and School</li>

#### Center for Arkansas History and Culture (UALR) &amp; Butler Center for Arkansas Studies (BC)

<li>Thibault Family Materials (MSS.04.16)</li><li>Gibson Family Papers (BC.MSS.97.56), containing legal documents related to the Thibaults</li><li>Carol Mann Gannaway Eruren Papers (BC.MSS.13.29), containing materials on both families</li><li>Pulaski County/Little Rock Records Collection (UALR.0173), including court records (1844–1890)</li><li>Chester Ashley Papers (UALR.MS.0091), including court documents from the Little Rock region and information on land claims and property maps of early nineteenth-century Arkansas</li>

#### University of Arkansas Libraries Special Collections

<li>“Cantrelle Witnesses a Letter for Engagés.” March 10, 1746. Core Family Papers (MC 1380, Box 21, File 7). Colonial Arkansas Post Ancestry Collection. Special Collections, University of Arkansas Libraries.</li>

#### UCA Archives &amp; Special Collections

<li>McGrew, DeAnn. "Origins of the Legend of Petit Jean." SMC 1202.</li><li>Rankin, Lucille Clerget. "The Legend of Petit Jean Mountain." 1946. PAM-1776.</li><li>Hardison, T. W. "A Place Called Petit Jean: The Mountain and Man's Mark." 1955. PAM-1777</li>

<a id="acknowledgements"></a>
### Acknowledgements

I am immensely grateful to the following people for lending their support and expertise: Buzz Arnold, Andy Beaupré, Everett Bandy, Victoria Chandler, John Gill, Jay Gitlin, Kimberly Green, Austin Headlee, Barclay Key, Harrison Mitchell, Kristin Mann, Terry Rasco, Jim Ross, Curtis Smith, Cheryl Vassaur, and the staffs of the Arkansas State Archives, UCA Archives &amp; Special Collections, and Archives Nationales d'Outre-mer.

<a id="community-sourcing"></a>
### Community Sourcing

This map is still very much a work-in-progress. I welcome suggestions, corrections, and alternative interpretations from folks who are much more familiar than I am with the history and geography of Arkansas. Please send to nemarvin [at] ualr.edu!

<a id="process-and-ethics"></a>
### Process and Ethics

The following document lays out the decision-making that went into the design of this resource, as well as goals for the future.

<p><a href="https://docs.google.com/document/d/1nveKuK7ZizGW68qqKHtMfWIL7R4hbBgaM0N6DY6mqWk/preview?tab=t.0#heading=h.k8r0oswh51bh" target="_blank" rel="noopener">Link to Process Document</a></p>

[↑ Back to Contents](#contents)

<script>
(function () {
  var reader = document.querySelector('.markdown-body');
  var settingsBox = document.getElementById('reader-settings');
  var resetButton = document.getElementById('reader-settings-reset');
  var status = document.getElementById('reader-settings-status');

  if (!reader || !settingsBox) return;

  var storageKey = 'arkansasCreoleReaderSettings';
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
