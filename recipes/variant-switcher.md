# Variant Switcher — Sticky Top-Right (MANDATORY)

Every multi-variant client demo gets this. Client clicks pill, sees variant. Shareable URL. Mobile-collapsed.

## Spec

- Position: `position: fixed; top: 20px; right: 20px; z-index: 99`
- 3 labeled pills (V1 / V2 / V3) — match variant names from `case-studies.md`
- Active pill: filled w/ accent color · inactive: outline
- Persist via URL hash `#v1` `#v2` `#v3` (shareable)
- Mobile (<768px): collapse to floating bottom-right circle button → modal sheet
- KILL component on production after client picks 1

## React + Tailwind (Next.js / Vite)

```tsx
"use client";
import { useEffect, useState } from "react";

const variants = [
  { id: "v1", label: "Editorial" },
  { id: "v2", label: "Cinematic" },
  { id: "v3", label: "Bold" },
];

export function VariantSwitcher() {
  const [active, setActive] = useState("v1");
  const [open, setOpen] = useState(false);

  useEffect(() => {
    const hash = window.location.hash.replace("#", "") || "v1";
    setActive(hash);
  }, []);

  const pick = (id: string) => {
    setActive(id);
    window.location.hash = id;
    setOpen(false);
  };

  return (
    <>
      {/* Desktop */}
      <div className="fixed top-5 right-5 z-[99] hidden md:flex gap-2 bg-black/85 backdrop-blur px-2 py-2 rounded-full border border-white/10">
        {variants.map((v) => (
          <button
            key={v.id}
            onClick={() => pick(v.id)}
            className={`px-4 py-2 rounded-full text-xs uppercase tracking-wider transition ${
              active === v.id
                ? "bg-[var(--accent)] text-black"
                : "text-white/70 hover:text-white"
            }`}
          >
            {v.label}
          </button>
        ))}
      </div>

      {/* Mobile floating button */}
      <button
        onClick={() => setOpen(!open)}
        className="fixed bottom-5 right-5 z-[99] md:hidden w-14 h-14 rounded-full bg-black text-white text-xs font-bold shadow-xl"
      >
        {active.toUpperCase()}
      </button>

      {/* Mobile modal sheet */}
      {open && (
        <div className="fixed inset-0 z-[100] md:hidden bg-black/80 flex items-end" onClick={() => setOpen(false)}>
          <div className="w-full bg-black p-6 rounded-t-3xl" onClick={(e) => e.stopPropagation()}>
            <p className="text-white/50 text-xs uppercase tracking-widest mb-4">Pick variant</p>
            {variants.map((v) => (
              <button
                key={v.id}
                onClick={() => pick(v.id)}
                className={`w-full text-left py-4 border-b border-white/10 ${
                  active === v.id ? "text-[var(--accent)]" : "text-white"
                }`}
              >
                {v.label} {active === v.id && "✓"}
              </button>
            ))}
          </div>
        </div>
      )}
    </>
  );
}
```

Then route by hash:

```tsx
// app/page.tsx OR src/App.tsx
import { useState, useEffect } from "react";
import V1Editorial from "./variants/V1Editorial";
import V2Cinematic from "./variants/V2Cinematic";
import V3Bold from "./variants/V3Bold";

export default function Page() {
  const [variant, setVariant] = useState("v1");

  useEffect(() => {
    const update = () => setVariant(window.location.hash.replace("#", "") || "v1");
    update();
    window.addEventListener("hashchange", update);
    return () => window.removeEventListener("hashchange", update);
  }, []);

  return (
    <>
      <VariantSwitcher />
      {variant === "v1" && <V1Editorial />}
      {variant === "v2" && <V2Cinematic />}
      {variant === "v3" && <V3Bold />}
    </>
  );
}
```

## Pure HTML / vanilla JS (Vow Sanctuary tier)

```html
<style>
.vs { position:fixed; top:20px; right:20px; z-index:99;
      display:flex; gap:8px; background:rgba(0,0,0,.85);
      backdrop-filter:blur(10px); padding:8px;
      border-radius:99px; border:1px solid rgba(255,255,255,.1); }
.vs button { padding:10px 18px; border-radius:99px;
             font-size:11px; letter-spacing:.12em; text-transform:uppercase;
             background:transparent; color:rgba(255,255,255,.7);
             border:none; cursor:pointer; transition:.2s; }
.vs button.active { background:var(--accent); color:#000; }
@media (max-width:768px) {
  .vs { top:auto; bottom:20px; right:20px; flex-direction:column; }
}
</style>

<div class="vs" id="vs">
  <button data-v="v1" class="active">Editorial</button>
  <button data-v="v2">Cinematic</button>
  <button data-v="v3">Bold</button>
</div>

<script>
const buttons = document.querySelectorAll('#vs button');
const route = () => {
  const v = location.hash.replace('#','') || 'v1';
  document.querySelectorAll('[data-variant]').forEach(el =>
    el.style.display = el.dataset.variant === v ? 'block' : 'none'
  );
  buttons.forEach(b => b.classList.toggle('active', b.dataset.v === v));
};
buttons.forEach(b => b.onclick = () => { location.hash = b.dataset.v; });
window.addEventListener('hashchange', route);
route();
</script>

<section data-variant="v1">...V1 markup...</section>
<section data-variant="v2" style="display:none">...V2 markup...</section>
<section data-variant="v3" style="display:none">...V3 markup...</section>
```

## Header-integrated variant (alternative placement)

If full nav header exists, drop switcher into top-right of nav:

```tsx
<header className="fixed top-0 inset-x-0 z-50 px-6 py-4 flex items-center justify-between bg-paper/90 backdrop-blur border-b border-rule">
  <div className="font-display italic text-xl">{brand}</div>
  <nav className="hidden md:flex gap-8 text-sm">
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#contact">Contact</a>
  </nav>
  <div className="flex items-center gap-3">
    <VariantSwitcherCompact />  {/* 3 mini pills */}
    <a href="#contact" className="bg-ink text-paper px-5 py-2.5 rounded-full text-sm">Inquire</a>
  </div>
</header>
```

## Client message (paste into pitch)

```
Demo has 3 variants — switch via top-right pills:

→ V1 Editorial — magazine grid, serif display, whitespace-heavy
→ V2 Cinematic — R3F 3D hero, dark, animation-forward
→ V3 Bold — glassmorphic, single accent, type-driven

Pick the one that feels right. I polish it + ship to your domain. The other 2 die.
```

## Production cleanup checklist

- [ ] Client picked variant
- [ ] Delete `<VariantSwitcher />` import + render
- [ ] Move winning variant from `variants/V2Cinematic.tsx` → `app/page.tsx`
- [ ] Delete other 2 variant files
- [ ] Remove `#v1` `#v2` `#v3` hash references
- [ ] Delete unused tokens / fonts from losing variants
- [ ] Re-deploy clean build
