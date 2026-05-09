# Gemini Watermark Remover

I reverse-engineered the site [gradually.ai/gemini-watermark-remover](https://www.gradually.ai/en/gemini-watermark-remover/) as of May 9, 2026.

You can find the snapshot for that date on archive.ph or the [Wayback Machine](https://web.archive.org/web/20260508203229/https://www.gradually.ai/en/gemini-watermark-remover/).

## Reverse Engineering Method

I would like to highlight the specific JavaScript chunk: [`08tipuo3xapm9.js`](https://www.gradually.ai/_next/static/chunks/08tipuo3xapm9.js?dpl=dpl_3VVxmETkXkj9KFtymAAnCERJkQPU).

To extract the relevant logic, open the console on [gradually.ai](https://www.gradually.ai/en/gemini-watermark-remover/) and run the following snippet:

```javascript
(async () => {
  const src = [...document.scripts]
    .find(s => s.src.includes("08tipuo3xapm9"))
    .src;

  const txt = await fetch(src).then(r => r.text());
  const idx = txt.indexOf("alphaMap");

  console.log(txt.slice(idx - 3000, idx + 6000));
})();
```

## Logo Assets

The logo assets used for mashing are listed below. If the links are broken, please use the archived links referenced above.

*   `https://www.gradually.ai/images/tools/gemini-watermark-48.png`
*   `https://www.gradually.ai/images/tools/gemini-watermark-96.png`
