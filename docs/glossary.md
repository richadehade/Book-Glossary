---
title: "Book Glossary"
layout: default
---

Welcome — this page lists book-related terms and concise definitions. Add entries under the correct heading or alphabetically.

## Navigation
- [A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · [H](#h) · [I](#i) · [J](#j) · [K](#k) · [L](#l) · [M](#m) · [N](#n) · [O](#o) · [P](#p) · [Q](#q) · [R](#r) · [S](#s) · [T](#t) · [U](#u) · [V](#v) · [W](#w) · [X](#x) · [Y](#y) · [Z](#z)

---

## A
1) Avarice - Extreme greed for wealth or material gain. <br>
2) Approbation - Approval or praise
---

## B


---

## C
1) Complacency - A feeling og calm satisfaction with your own abilities or situation that prevents you from trying harder. <br>
2) Cantankerous - Argumentative, difficult to deal with
---
## D
1) Despondent - Unhappy & with no hope or enthusiasm 
---
## E

---
## F

---

## G
1) Guck - A slimy, sticky, unpleasant substance.<br>
---

## H

---

## I

---
## J

---
## K

---
## L

---
## M

---
## N
<!-- Next page floating button + accessible label -->
<style>
/* simple floating circular button in the lower-right corner */
.next-page-btn {
  position: fixed;
  right: 18px;
  bottom: 18px;
  background: #0366d6;
  color: #fff;
  border-radius: 999px;
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 6px 18px rgba(3,102,214,0.2);
  text-decoration: none;
  font-weight: 600;
  font-size: 22px;
  line-height: 1;
  z-index: 1000;
  transition: transform .12s ease, box-shadow .12s ease;
}
.next-page-btn:hover { transform: translateY(-3px); box-shadow: 0 10px 24px rgba(3,102,214,0.22); }

/* small visible label on non-touch devices */
.next-page-label {
  position: fixed;
  right: 78px;
  bottom: 24px;
  background: rgba(3,102,214,0.95);
  color: #fff;
  padding: 6px 10px;
  border-radius: 6px;
  font-size: 13px;
  z-index: 1000;
  display: none;
}

/* reduce motion preference */
@media (prefers-reduced-motion: reduce) {
  .next-page-btn { transition: none; transform: none; }
}
</style>

<a id="next-page" class="next-page-btn" href="#" aria-label="Go to N–Z glossary" title="Next: N–Z">→</a>
<span id="next-label" class="next-page-label" aria-hidden="true">Next: N–Z</span>

<script>
(function () {
  // target page base (no extension). script will test common candidates
  const base = './glossary-n-z';
  // where on the target page we want to land; make sure glossary-n-z uses explicit anchor {#n}
  const anchor = '#n';
  const candidates = [base + '.html', base + '/', base];

  const btn = document.getElementById('next-page');
  const label = document.getElementById('next-label');

  // show label on hover (desktop)
  btn.addEventListener('mouseenter', () => { label.style.display = 'block'; });
  btn.addEventListener('mouseleave', () => { label.style.display = 'none'; });

  // attempt to locate a valid URL and navigate there (HEAD requests)
  async function goToNext() {
    for (const c of candidates) {
      try {
        // HEAD is lighter than GET; works for same-origin (GitHub Pages)
        const resp = await fetch(c, { method: 'HEAD' });
        if (resp.ok) {
          window.location.href = c + anchor;
          return;
        }
      } catch (e) {
        // ignore and try next candidate
      }
    }
    // fallback: try .html anyway
    window.location.href = base + '.html' + anchor;
  }

  btn.addEventListener('click', function (e) {
    e.preventDefault();
    goToNext();
  });

  // keyboard support: Enter/Space while focused
  btn.addEventListener('keydown', function (e) {
    if (e.key === 'Enter' || e.key === ' ') {
      e.preventDefault();
      goToNext();
    }
  });
})();
</script>
---
