# stevenuniverse.github.io
<!doctype html>
<html lang="en"><head><script>window["__codeletBootstrap__"]=JSON.parse('{"A":"A","B":"20260717-05-8209e4e"}');</script><script src="/_sdk/f432b76fb310b513.telemetry_sdk.js" integrity="sha512-9FJQ55EKmmqhyyik8BhrMVfm0+iYYfb8uOlRsjtkxJMEI97qOVEI4PnHohDjQAtvAep0IOEpdQ64eki0sz62ug=="></script>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Crystal Gem Alignment Chart</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800&amp;family=Playfair+Display:wght@700;800&amp;display=swap" rel="stylesheet">
  <style>
    :root {
      --ink: #512044;
      --muted: #865472;
      --rose: #ec5d9f;
      --rose-dark: #ad275f;
      --rose-hot: #ff74b5;
      --peach: #ffb69e;
      --cream: #fff8f4;
      --panel: #fffafc;
      --line: #e8bad2;
      --label-pink: #f8c5dc;
      --label-light: #ffe2ee;
      --lavender: #b393d8;
      --cell: 64px;
      --label: 132px;
    }

    * { box-sizing: border-box; }

    html, body {
      margin: 0;
      width: 100%;
      min-height: 100%;
    }

    body {
      font-family: "DM Sans", sans-serif;
      color: var(--ink);
      overflow-x: hidden;
    }

    button, input, select, textarea { font: inherit; }

    .app-wrapper {
      position: relative;
      width: 100%;
      min-height: 100%;
      overflow: hidden;
      padding: clamp(16px, 3vw, 42px);
      background-image:
        radial-gradient(circle at 12% 16%, rgba(255,255,255,.82) 0 2px, transparent 3px),
        radial-gradient(circle at 87% 10%, rgba(255,255,255,.7) 0 3px, transparent 4px),
        radial-gradient(circle at 72% 26%, rgba(255,255,255,.6) 0 1px, transparent 2px),
        linear-gradient(rgba(173,39,95,.035) 1px, transparent 1px),
        linear-gradient(90deg, rgba(173,39,95,.035) 1px, transparent 1px);
      background-size: 180px 180px, 260px 260px, 120px 120px, 24px 24px, 24px 24px;
    }

    .app-wrapper::before,
    .app-wrapper::after {
      content: "";
      position: absolute;
      z-index: 0;
      pointer-events: none;
      opacity: .5;
      filter: drop-shadow(0 10px 16px rgba(123, 36, 88, .12));
      transform: rotate(45deg);
    }

    .app-wrapper::before {
      top: 48px;
      right: 7%;
      width: 82px;
      height: 82px;
      border: 2px solid rgba(255,255,255,.85);
      border-radius: 20px;
      background: linear-gradient(135deg, rgba(255,255,255,.52), rgba(236,93,159,.2));
    }

    .app-wrapper::after {
      left: 3%;
      bottom: 40px;
      width: 52px;
      height: 52px;
      border: 2px solid rgba(255,255,255,.72);
      border-radius: 14px;
      background: linear-gradient(135deg, rgba(179,147,216,.35), rgba(255,182,158,.35));
    }

    .main-content {
      position: relative;
      z-index: 1;
      width: 100%;
      max-width: 1500px;
      margin: 0 auto;
    }

    .top-bar {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      gap: 24px;
      margin-bottom: 20px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 10px;
      color: var(--rose-dark);
      font-size: 11px;
      font-weight: 800;
      letter-spacing: .17em;
      text-transform: uppercase;
    }

    .eyebrow::before {
      content: "★";
      display: grid;
      place-items: center;
      width: 25px;
      height: 25px;
      border-radius: 50%;
      background: var(--rose);
      color: white;
      font-size: 12px;
      box-shadow: 0 5px 12px rgba(173,39,95,.24);
    }

    .title {
      margin: 0;
      max-width: 790px;
      font-family: "Playfair Display", serif;
      line-height: .98;
      letter-spacing: -.045em;
      text-shadow: 0 3px 0 rgba(255,255,255,.62);
    }

    .subtitle {
      margin: 12px 0 0;
      max-width: 680px;
      line-height: 1.55;
    }

    .instruction-card {
      position: relative;
      flex: 0 1 350px;
      display: flex;
      align-items: flex-start;
      gap: 11px;
      padding: 15px 17px;
      overflow: hidden;
      border: 1px solid rgba(173,39,95,.2);
      border-radius: 22px 22px 22px 7px;
      box-shadow: 0 12px 28px rgba(91,28,68,.12);
    }

    .instruction-card::after {
      content: "✦";
      position: absolute;
      right: 13px;
      bottom: 4px;
      color: rgba(236,93,159,.25);
      font-size: 31px;
    }

    .instruction-card svg {
      flex: none;
      width: 20px;
      height: 20px;
      margin-top: 1px;
      color: var(--rose-dark);
    }

    .instruction-card p {
      position: relative;
      z-index: 1;
      margin: 0;
      line-height: 1.45;
    }

    .chart-shell {
      width: 100%;
      overflow: hidden;
      border: 2px solid rgba(173,39,95,.2);
      border-radius: 26px;
      box-shadow:
        0 24px 65px rgba(91,28,68,.17),
        0 0 0 6px rgba(255,255,255,.34);
    }

    .chart-toolbar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      min-height: 62px;
      padding: 11px 15px;
      border-bottom: 1px solid rgba(173,39,95,.18);
    }

    .legend {
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 14px;
    }

    .legend-item {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      font-size: 12px;
      font-weight: 600;
    }

    .swatch {
      width: 18px;
      height: 18px;
      border: 1px solid var(--line);
      border-radius: 50% 50% 50% 7px;
      background: #fffafd;
    }

    .swatch.marked {
      border-color: var(--rose);
      background: linear-gradient(135deg, var(--rose-hot), var(--rose));
      box-shadow: 0 3px 8px rgba(173,39,95,.2);
    }

    .toolbar-actions {
      display: flex;
      align-items: center;
      gap: 9px;
    }

    .counter {
      min-width: 86px;
      padding: 8px 11px;
      border: 1px solid rgba(173,39,95,.12);
      border-radius: 999px;
      background: rgba(255,255,255,.64);
      color: var(--rose-dark);
      font-size: 12px;
      font-weight: 800;
      text-align: center;
    }

    .clear-control {
      display: inline-flex;
      align-items: center;
      min-height: 36px;
      overflow: hidden;
      border: 1px solid rgba(173,39,95,.24);
      border-radius: 12px;
      background: white;
      box-shadow: 0 4px 10px rgba(91,28,68,.06);
    }

    .clear-control button {
      min-height: 36px;
      padding: 7px 12px;
      border: 0;
      background: transparent;
      color: var(--ink);
      cursor: pointer;
      font-size: 12px;
      font-weight: 700;
      transition: background .15s ease, transform .15s ease;
    }

    .clear-control button:hover {
      background: rgba(236,93,159,.1);
    }

    .clear-control button:active { transform: scale(.97); }

    .clear-control .danger {
      color: white;
    }

    .clear-control .cancel {
      border-left: 1px solid rgba(173,39,95,.15);
    }

    .matrix-scroll {
      position: relative;
      width: 100%;
      max-height: calc(72 * min(var(--vh, 1vh), 1vh));
      overflow: auto;
      overscroll-behavior: contain;
      scrollbar-color: var(--rose) #ffe5f0;
      scrollbar-width: thin;
    }

    .matrix-scroll::-webkit-scrollbar { width: 12px; height: 12px; }
    .matrix-scroll::-webkit-scrollbar-track { background: #ffe5f0; }
    .matrix-scroll::-webkit-scrollbar-thumb {
      border: 3px solid #ffe5f0;
      border-radius: 999px;
      background: var(--rose);
    }

    .matrix {
      display: grid;
      grid-template-columns: var(--label) repeat(34, var(--cell));
      grid-template-rows: 132px repeat(34, var(--cell));
      width: max-content;
      min-width: 100%;
      gap: 1px;
      background: var(--line);
    }

    .corner {
      position: sticky;
      top: 0;
      left: 0;
      z-index: 8;
      display: flex;
      align-items: flex-end;
      justify-content: flex-start;
      padding: 12px;
      background:
        linear-gradient(135deg, transparent 49.4%, rgba(81,32,68,.18) 49.5%, rgba(81,32,68,.18) 50.5%, transparent 50.6%),
        linear-gradient(135deg, #ef83b5, #f8b6d2);
    }

    .corner::after {
      content: "★";
      position: absolute;
      top: 12px;
      right: 13px;
      color: rgba(255,255,255,.86);
      font-size: 24px;
      text-shadow: 0 3px 8px rgba(173,39,95,.25);
    }

    .corner span {
      max-width: 94px;
      font-size: 10px;
      font-weight: 800;
      line-height: 1.2;
      letter-spacing: .08em;
      text-transform: uppercase;
    }

    .column-label {
      position: sticky;
      top: 0;
      z-index: 6;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      overflow: visible;
      background: linear-gradient(180deg, var(--label-light), var(--label-pink));
      transition: background .15s ease, color .15s ease;
    }

    .column-label span {
      display: inline-block;
      width: 140px;
      padding: 0 0 16px 4px;
      overflow: visible;
      color: inherit;
      font-size: 11px;
      font-weight: 700;
      text-align: left;
      white-space: nowrap;
      transform: rotate(-45deg);
      transform-origin: 10px 100%;
    }

    .row-label {
      position: sticky;
      left: 0;
      z-index: 5;
      display: flex;
      align-items: center;
      justify-content: flex-end;
      min-width: var(--label);
      padding: 0 11px;
      overflow: hidden;
      background: linear-gradient(90deg, var(--label-light), var(--label-pink));
      color: var(--ink);
      font-size: 11px;
      font-weight: 700;
      text-align: right;
      text-overflow: ellipsis;
      white-space: nowrap;
      transition: background .15s ease, color .15s ease;
    }

    .row-label::before {
      content: "✦";
      margin-right: 6px;
      color: rgba(173,39,95,.42);
      font-size: 9px;
    }

    .row-label.is-active,
    .column-label.is-active {
      background: linear-gradient(135deg, var(--rose-hot), var(--rose));
      color: white !important;
    }

    .row-label.is-active::before { color: white; }

    .matrix-cell {
      position: relative;
      display: block;
      width: var(--cell);
      height: var(--cell);
      padding: 0;
      background: #fffafd;
      transition: background .12s ease, box-shadow .12s ease, transform .12s ease;
    }

    .matrix-cell:hover,
    .matrix-cell:focus-within {
      z-index: 2;
      background: #fff0f7;
      box-shadow: inset 0 0 0 2px var(--rose);
    }

    .matrix-cell.is-marked {
      background:
        radial-gradient(circle at center, rgba(255,255,255,.92) 0 7px, transparent 8px),
        linear-gradient(135deg, #ffd5e8, #ffb9d7);
      box-shadow: inset 0 0 0 1px var(--rose);
    }

    .matrix-cell.is-marked::after {
      content: "★";
      position: absolute;
      top: 2px;
      right: 4px;
      pointer-events: none;
      color: rgba(173,39,95,.35);
      font-size: 9px;
    }

    .matrix-cell-input {
      position: relative;
      z-index: 1;
      width: 100%;
      height: 100%;
      border: 0;
      padding: 5px;
      background: transparent;
      color: var(--ink);
      font-size: 11px;
      font-weight: 600;
      text-align: center;
      outline: none;
    }

    .matrix-cell-input::placeholder {
      color: rgba(173,39,95,.23);
    }

    .matrix-cell-input:focus-visible,
    .clear-control button:focus-visible {
      z-index: 9;
      outline: 3px solid #8c2562;
      outline-offset: -3px;
    }

    .status {
      position: absolute;
      width: 1px;
      height: 1px;
      padding: 0;
      margin: -1px;
      overflow: hidden;
      clip: rect(0, 0, 0, 0);
      white-space: nowrap;
      border: 0;
    }

    @media (max-width: 760px) {
      :root {
        --cell: 56px;
        --label: 110px;
      }

      .app-wrapper { padding: 14px; }
      .top-bar { align-items: stretch; flex-direction: column; gap: 14px; }
      .instruction-card { flex-basis: auto; }
      .chart-shell { border-radius: 19px; }
      .chart-toolbar { align-items: flex-start; flex-direction: column; }
      .toolbar-actions { width: 100%; justify-content: space-between; }
      .matrix { grid-template-rows: 114px repeat(34, var(--cell)); }
      .column-label span, .row-label { font-size: 10px; }
    }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        scroll-behavior: auto !important;
        transition-duration: .01ms !important;
        animation-duration: .01ms !important;
      }
    }
  </style>
  <script src="/_sdk/e3937a0574eb2d69.data_sdk.js" type="text/javascript" integrity="sha512-xbp/ACqEQy1aDxYMtXTrR3y5MUbzxuggRR/9sD48Gl4VhLMMCiAHsxMaFV6DTdeBpR6ymF+t2zhPKYkWM3+Jfw=="></script>
  <script src="/_sdk/9432170dbd2ae0df.resizing_sdk.js" type="text/javascript" integrity="sha512-FeT+58sb1f9ejWPWFjCbJvTT+SDwGV+ngrHUnlO7TWEOoqwOLj6p256kO3vOL7DIWl1cIgrobiof8v2bOigwPg=="></script>
 </head>
 <body data-template-id="__page-root" style="background: linear-gradient(135deg, rgb(255, 214, 232), rgb(245, 185, 217) 48%, rgb(255, 197, 180));">
  <div class="app-wrapper">
   <main class="main-content">
    <header class="top-bar">
     <div>
      <div class="eyebrow" aria-hidden="true">
       Crystal Gem Matrix · 34 × 34
      </div>
      <h1 data-template-id="chart-title" class="canva-text title" style="color: rgb(118, 38, 80); font-weight: 800; font-style: normal; font-size: 48px; letter-spacing: -0.05rem; line-height: 1;">Crystal Gem Alignment</h1>
      <p data-template-id="chart-subtitle" class="canva-text subtitle" style="color: rgb(123, 70, 101); font-weight: 400; font-style: normal; font-size: 16px; line-height: 1.5;">Map every pairing across a constellation of 34 sparkling personalities.</p>
     </div>
     <aside data-template-id="instruction-card" class="canva-card instruction-card" style="background: linear-gradient(135deg, rgb(255, 250, 253), rgb(255, 229, 241));"><i data-lucide="gem" aria-hidden="true"></i>
      <p data-template-id="chart-instructions" class="canva-text" style="color: rgb(102, 51, 79); font-weight: 400; font-style: normal; font-size: 13px; line-height: 1.45;">Type a note, symbol, or tiny gem into any box. Row and column names stay pinned while you explore.</p>
     </aside>
    </header>
    <section data-template-id="chart-panel" class="canva-panel chart-shell" aria-label="Alignment matrix" style="background: rgb(255, 250, 253);">
     <div data-template-id="toolbar" class="canva-menu chart-toolbar" style="background: linear-gradient(to right, rgb(255, 244, 249), rgb(255, 224, 237));">
      <div class="legend" aria-label="Legend"><span class="legend-item"> <span class="swatch" aria-hidden="true"></span> <span data-template-id="legend-empty" class="canva-text" style="color: rgb(134, 84, 114); font-weight: 600; font-style: normal; font-size: 12px;">Uncharted</span> </span> <span class="legend-item"> <span class="swatch marked" aria-hidden="true"></span> <span data-template-id="legend-marked" class="canva-text" style="color: rgb(134, 84, 114); font-weight: 600; font-style: normal; font-size: 12px;">Gem marked</span> </span>
      </div>
      <div class="toolbar-actions"><output id="selection-count" class="counter" aria-live="polite">0 filled</output>
       <div class="clear-control"><button id="clear-start" data-template-id="clear-button" class="canva-button" type="button" style="color: rgb(118, 38, 80); font-weight: 700; font-style: normal; font-size: 12px;">Clear all</button>
        <div id="clear-confirmation" class="hidden"><button id="clear-confirm" data-template-id="confirm-clear-button" class="canva-button danger" type="button" style="background: linear-gradient(135deg, rgb(236, 93, 159), rgb(184, 47, 107)); color: rgb(255, 255, 255); font-weight: 700; font-style: normal; font-size: 12px;">Confirm clear</button> <button id="clear-cancel" data-template-id="cancel-clear-button" class="canva-button cancel" type="button" style="background: rgb(255, 255, 255); color: rgb(118, 38, 80); font-weight: 700; font-style: normal; font-size: 12px;">Cancel</button>
        </div>
       </div>
      </div>
     </div>
     <div id="matrix-scroll" class="matrix-scroll" tabindex="0" aria-label="Scrollable alignment chart">
      <div id="matrix" class="matrix" role="grid" aria-rowcount="35" aria-colcount="35">
       <div data-template-id="corner-label" class="canva-text corner" role="columnheader" style="color: rgb(101, 33, 68); font-weight: 800; font-style: normal; font-size: 10px;">Gems × Gems</div>
       <div data-template-id="column-01" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Sagaci</div>
       <div data-template-id="column-02" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Angel</div>
       <div data-template-id="column-03" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Nate</div>
       <div data-template-id="column-04" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Hanako</div>
       <div data-template-id="column-05" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Mari</div>
       <div data-template-id="column-06" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Azzy</div>
       <div data-template-id="column-07" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Nyomi</div>
       <div data-template-id="column-08" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Charlie</div>
       <div data-template-id="column-09" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Kotoha</div>
       <div data-template-id="column-10" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Magma</div>
       <div data-template-id="column-11" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Cath</div>
       <div data-template-id="column-12" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Dove</div>
       <div data-template-id="column-13" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Bee</div>
       <div data-template-id="column-14" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Yuna</div>
       <div data-template-id="column-15" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Eli</div>
       <div data-template-id="column-16" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Viki</div>
       <div data-template-id="column-17" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Hannah</div>
       <div data-template-id="column-18" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Terrell</div>
       <div data-template-id="column-19" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Nova</div>
       <div data-template-id="column-20" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Lani</div>
       <div data-template-id="column-21" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Merlin</div>
       <div data-template-id="column-22" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Noura</div>
       <div data-template-id="column-23" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Kerosene</div>
       <div data-template-id="column-24" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Diana</div>
       <div data-template-id="column-25" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Altima</div>
       <div data-template-id="column-26" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Graves</div>
       <div data-template-id="column-27" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Raven</div>
       <div data-template-id="column-28" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Silly Chris</div>
       <div data-template-id="column-29" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Dark</div>
       <div data-template-id="column-30" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Choco</div>
       <div data-template-id="column-31" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Lotus</div>
       <div data-template-id="column-32" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Kipsie</div>
       <div data-template-id="column-33" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Surf</div>
       <div data-template-id="column-34" class="canva-text column-label" role="columnheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Connor</div>
       <div data-template-id="row-01" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Sagaci</div>
       <div data-template-id="row-02" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Angel</div>
       <div data-template-id="row-03" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Nate</div>
       <div data-template-id="row-04" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Hanako</div>
       <div data-template-id="row-05" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Mari</div>
       <div data-template-id="row-06" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Azzy</div>
       <div data-template-id="row-07" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Nyomi</div>
       <div data-template-id="row-08" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Charlie</div>
       <div data-template-id="row-09" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Kotoha</div>
       <div data-template-id="row-10" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Magma</div>
       <div data-template-id="row-11" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Cath</div>
       <div data-template-id="row-12" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Dove</div>
       <div data-template-id="row-13" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Bee</div>
       <div data-template-id="row-14" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Yuna</div>
       <div data-template-id="row-15" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Eli</div>
       <div data-template-id="row-16" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Viki</div>
       <div data-template-id="row-17" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Hannah</div>
       <div data-template-id="row-18" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Terrell</div>
       <div data-template-id="row-19" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Nova</div>
       <div data-template-id="row-20" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Lani</div>
       <div data-template-id="row-21" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Merlin</div>
       <div data-template-id="row-22" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Noura</div>
       <div data-template-id="row-23" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Kerosene</div>
       <div data-template-id="row-24" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Diana</div>
       <div data-template-id="row-25" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Altima</div>
       <div data-template-id="row-26" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Graves</div>
       <div data-template-id="row-27" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Raven</div>
       <div data-template-id="row-28" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Silly Chris</div>
       <div data-template-id="row-29" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Dark</div>
       <div data-template-id="row-30" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Choco</div>
       <div data-template-id="row-31" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Lotus</div>
       <div data-template-id="row-32" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Kipsie</div>
       <div data-template-id="row-33" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Surf</div>
       <div data-template-id="row-34" class="canva-text row-label" role="rowheader" style="color: rgb(81, 32, 68); font-weight: 700; font-style: normal; font-size: 11px;">Connor</div>
      </div>
     </div>
    </section>
    <p id="status" class="status" aria-live="polite"></p>
   </main>
  </div>
  <script src="/_sdk/b7bbbe551ba4f8f5.editing_sdk.js" integrity="sha512-h06pMz6KcVo4Wjvoggb4sS5DZpb55bTriAzBmA0YwbkBA3z2ZXl8CBEbCWT+/fAsm0SwDejJ7jJHOZsLZKqPoQ=="></script>
  <script>
    const names = [
      "Sagaci", "Angel", "Nate", "Hanako", "Mari", "Azzy", "Nyomi", "Charlie",
      "Kotoha", "Magma", "Cath", "Dove", "Bee", "Yuna", "Eli", "Viki", "Hannah",
      "Terrell", "Nova", "Lani", "Merlin", "Noura", "Kerosene", "Diana", "Altima",
      "Graves", "Raven", "Silly Chris", "Dark", "Choco", "Lotus", "Kipsie", "Surf",
      "Connor"
    ];

    const matrix = document.getElementById("matrix");
    const countOutput = document.getElementById("selection-count");
    const status = document.getElementById("status");
    const rowLabels = [...document.querySelectorAll(".row-label")];
    const columnLabels = [...document.querySelectorAll(".column-label")];
    const clearStart = document.getElementById("clear-start");
    const clearConfirmation = document.getElementById("clear-confirmation");
    const clearConfirm = document.getElementById("clear-confirm");
    const clearCancel = document.getElementById("clear-cancel");
    let markedCount = 0;

    function updateCount() {
      countOutput.textContent = `${markedCount} filled`;
    }

    function setHeaderHighlight(rowIndex, columnIndex, active) {
      rowLabels[rowIndex].classList.toggle("is-active", active);
      columnLabels[columnIndex].classList.toggle("is-active", active);
    }

    function handleCellInput(cell, input) {
      const hasValue = input.value.trim() !== "";
      const wasMarked = cell.classList.contains("is-marked");

      if (hasValue && !wasMarked) {
        cell.classList.add("is-marked");
        markedCount++;
        updateCount();
      } else if (!hasValue && wasMarked) {
        cell.classList.remove("is-marked");
        markedCount--;
        updateCount();
      }
    }

    function createCell(rowIndex, columnIndex) {
      const cell = document.createElement("div");
      cell.className = "matrix-cell";
      cell.dataset.row = String(rowIndex);
      cell.dataset.column = String(columnIndex);

      const input = document.createElement("input");
      input.type = "text";
      input.className = "matrix-cell-input";
      input.placeholder = "✦";
      input.setAttribute("aria-label", `Cell at ${names[rowIndex]} and ${names[columnIndex]}`);

      input.addEventListener("input", () => handleCellInput(cell, input));
      input.addEventListener("mouseenter", () => setHeaderHighlight(rowIndex, columnIndex, true));
      input.addEventListener("mouseleave", () => setHeaderHighlight(rowIndex, columnIndex, false));
      input.addEventListener("focus", () => setHeaderHighlight(rowIndex, columnIndex, true));
      input.addEventListener("blur", () => setHeaderHighlight(rowIndex, columnIndex, false));

      cell.appendChild(input);
      return cell;
    }

    rowLabels.forEach((rowLabel, rowIndex) => {
      matrix.appendChild(rowLabel);
      names.forEach((_, columnIndex) => {
        matrix.appendChild(createCell(rowIndex, columnIndex));
      });
    });

    clearStart.addEventListener("click", () => {
      clearStart.classList.add("hidden");
      clearConfirmation.classList.remove("hidden");
      clearConfirm.focus();
    });

    clearCancel.addEventListener("click", () => {
      clearConfirmation.classList.add("hidden");
      clearStart.classList.remove("hidden");
      clearStart.focus();
    });

    clearConfirm.addEventListener("click", () => {
      document.querySelectorAll(".matrix-cell-input").forEach(input => {
        input.value = "";
      });
      document.querySelectorAll(".matrix-cell.is-marked").forEach(cell => {
        cell.classList.remove("is-marked");
      });
      markedCount = 0;
      updateCount();
      status.textContent = "All gem matrix cells cleared.";
      clearConfirmation.classList.add("hidden");
      clearStart.classList.remove("hidden");
      clearStart.focus();
    });

    updateCount();
    lucide.createIcons();
  </script>
 
</body></html>
