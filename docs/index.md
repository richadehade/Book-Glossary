---
title: "Book Glossary Home"
layout: default
---

# Book Glossary

Welcome to the Book Glossary for this repository.

<label for="letter-select">Jump to letter:</label>
<select id="letter-select" aria-label="Jump to letter">
  <option value="">Select a letter…</option>
</select>

<p>
  - <a href="./glossary.md">Open the Glossary</a>
</p>

<noscript>
  <p><strong>JavaScript is required for the dropdown.</strong> Use the glossary link above or the alphabet links below:</p>
  <p>
    <a href="./glossary.md#A">A</a> · <a href="./glossary.md#B">B</a> · <a href="./glossary.md#C">C</a> · <a href="./glossary.md#D">D</a> · <a href="./glossary.md#E">E</a> · <a href="./glossary.md#F">F</a> · <a href="./glossary.md#G">G</a> · <a href="./glossary.md#H">H</a> · <a href="./glossary.md#I">I</a> · <a href="./glossary.md#J">J</a> · <a href="./glossary.md#K">K</a> · <a href="./glossary.md#L">L</a> · <a href="./glossary.md#M">M</a> · <a href="./glossary.md#N">N</a> · <a href="./glossary.md#O">O</a> · <a href="./glossary.md#P">P</a> · <a href="./glossary.md#Q">Q</a> · <a href="./glossary.md#R">R</a> · <a href="./glossary.md#S">S</a> · <a href="./glossary.md#T">T</a> · <a href="./glossary.md#U">U</a> · <a href="./glossary.md#V">V</a> · <a href="./glossary.md#W">W</a> · <a href="./glossary.md#X">X</a> · <a href="./glossary.md#Y">Y</a> · <a href="./glossary.md#Z">Z</a>
  </p>
</noscript>

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

  // Build anchor string the same way GitHub Pages/Jekyll typically does:
  // single letters -> lowercase (e.g. A -> a). If your headings are more complex,
  // use explicit IDs in glossary.md (see notes below).
  select.addEventListener('change', function() {
    const val = this.value;
    if (!val) return;
    const anchor = '#' + val.toLowerCase();

    // Candidate resource paths (checked in order)
    const candidates = [
      './glossary.html',
      './glossary/',
      './glossary',     // some setups serve glossary as /glossary
      './glossary.md'   // fallback (may 404 on Pages)
    ];

    // Try each candidate and navigate to the first that exists.
    // We fetch without the fragment (fragment isn't sent to server).
    (async function() {
      for (const base of candidates) {
        try {
          const resp = await fetch(base, { method: 'GET' });
          if (resp.ok) {
            window.location.href = base + anchor;
            return;
          }
        } catch (e) {
          // ignore and try next candidate
        }
      }
      // If none found, navigate to the README fallback (or the raw markdown)
      window.location.href = './glossary.html' + anchor;
    })();
  });
})();
</script>
