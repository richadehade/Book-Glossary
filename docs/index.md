---
title: "Book Glossary Home"
layout: default
---

Welcome to the Book Glossary for this repository.

<label for="letter-select">Jump to letter:</label>
<select id="letter-select" aria-label="Jump to letter">
  <option value="">Select a letter…</option>
</select>

<p>
  - <a href="./glossary.md">Open the Glossary (overview)</a>
  - <a href="./glossary-a-m.md">Glossary A–M</a>
  - <a href="./glossary-n-z.md">Glossary N–Z</a>
</p>

<script>
(function () {
  const select = document.getElementById('letter-select');
  const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('');
  letters.forEach(function(letter) {
    const opt = document.createElement('option');
    opt.value = letter;
    opt.textContent = letter;
    select.appendChild(opt);
  });

  // map letter -> page that contains it
  function pageForLetter(letter) {
    const code = letter.charCodeAt(0);
    // A–M (65..77) -> glossary-a-m
    if (code >= 65 && code <= 77) return './glossary-a-m';
    // N–Z -> glossary-n-z
    return './glossary-n-z';
  }

  // Helper to try likely paths and then navigate with anchor
  async function navigateTo(base, anchor) {
    const candidates = [base + '.html', base + '/', base]; // tests .html, directory, raw
    for (const candidate of candidates) {
      try {
        const resp = await fetch(candidate, { method: 'HEAD' });
        if (resp.ok) {
          window.location.href = candidate + anchor;
          return true;
        }
      } catch (e) {
        // continue trying
      }
    }
    // fallback: try .html anyway
    window.location.href = base + '.html' + anchor;
    return false;
  }

  select.addEventListener('change', function() {
    const val = this.value;
    if (!val) return;
    const anchor = '#' + val.toLowerCase(); // explicit anchors in target pages use lowercase single letters
    const base = pageForLetter(val);
    navigateTo(base, anchor);
  });
})();
</script>
