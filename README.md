# Music-sheet-scroller
Auto identify and scroll music sheet
A self-contained sheet-music / tab auto-scroller. Load a PDF, set the tempo,
and the page rolls itself at the right speed while a highlight tracks the line
you're on. Everything runs locally in your browser — your PDF is never uploaded.

HOW TO OPEN
-----------
Easiest: double-click  index.html  — it opens in your default browser.
(Works in Chrome, Edge, Firefox, Safari, and their mobile versions.)

Keep the "lib" folder next to index.html. It contains the PDF engine that
makes everything work offline. If you move index.html, move the whole folder.

OPTIONAL — run a tiny local server (best performance, no browser warnings):
  1. Open a terminal in this folder.
  2. Run one of:
       python3 -m http.server 8000
       (or)  npx serve .
  3. Open  http://localhost:8000  in your browser.

USING IT
--------
1. Click "Load PDF" (or drag a PDF onto the page).
2. Set Beats Per Minute and the time signature.
3. Tell it how the page is laid out (measures per line). Auto-detect finds the
   staff lines for you; turn it off to fall back to even spacing.
4. Tap any line to choose where to start.
5. Press the round Play button (or the spacebar).

The status light by the Reset button is green while playing, red when stopped.

SHORTCUTS
---------
  Space  play / pause
  R      reset to the top
  F      fullscreen
  Up/Dn  jump one line
  Tap a line  set it as the start point

CONTROLS
--------
  Auto-detect staff lines   find each music line automatically
  Show line tracker         show/hide the highlight band
  Fit each page to screen   one whole page per screen (good for portrait)
  Metronome click           audible click on the beat
  1-bar count-in            one bar of clicks before it starts rolling
  Reading guide line        a faint line at the reading position
  Speed fine-tune           nudge the scroll speed if it drifts

NOTES
-----
- Detection works best on regularly engraved scores. If a busy page merges two
  lines, use the line tracker + tap-to-start, or switch auto-detect off.
- No internet required. (If online, it also pulls nicer display fonts; offline
  it uses your system fonts — function is identical either way.)

INSTALL AS AN APP ON IPAD / IPHONE (PWA)
----------------------------------------
This package is also a Progressive Web App, so you can install it to the Home
Screen and run it fullscreen, offline, like a real app. You must open it from a
URL once (not from the Files app) so it can cache itself:

  1. Put the RollScore folder on a server it can be reached from. Easiest:
     - Free hosting: drag the folder onto https://app.netlify.com/drop (or use
       GitHub Pages). You'll get a URL.
     - Or a local-server app on the iPad (e.g. WorldWideWeb) pointed at the folder.
  2. Open that URL in Safari on the iPad and let the page finish loading once.
  3. Tap the Share button → "Add to Home Screen" → Add.
  4. Launch it from the new icon. After that first online load it works offline.

Notes:
  - Must be opened over http/https for the offline cache to register; opening a
    local file directly will not install it.
  - Use portrait for one-page-per-screen; the app's own controls handle layout.
