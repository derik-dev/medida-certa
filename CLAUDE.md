# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Institutional landing page for **Clínica Medida Certa**, a Brazilian health clinic (Psicologia, Nutrição, Geriatria, Neuropsicologia). The site is fully static — no build step, no package manager, no bundler.

## Running Locally

Open `index.html` directly in a browser, or use VS Code Live Server for auto-reload on save. There is no `npm install`, no `build`, no `dev` command.

## File Structure

- `index.html` — all page sections and CDN imports for Tailwind, GSAP, Lenis, Swiper
- `style.css` — CSS custom properties (color palette, fonts), component styles, glassmorphism, and layout overrides that can't be expressed with Tailwind utilities
- `script.js` — GSAP/ScrollTrigger animations, Lenis smooth scroll, Swiper carousel, magnetic button effect, nav scroll state, and Groq chatbot logic
- `briefing.md` — brand identity reference (colors, tone, target audience)

## Architecture Notes

**Styling:** Tailwind CSS (CDN) handles utilities; `style.css` owns complex components. Color palette is defined as CSS variables in `:root` — always use those variables (`--azul-clinico`, `--verde-suave`, `--bege-claro`, `--azul-escuro`, etc.) instead of hardcoding hex values.

**Animations:** GSAP with ScrollTrigger. Elements with `.reveal-fade` get a universal scroll-triggered fade-in. Hero title uses `.#hero-title span` kinetic reveal. Lenis must be initialized before GSAP ScrollTrigger for smooth scroll to work correctly.

**Carousels:** Two separate systems — Swiper.js (testimonials/results section) and a custom infinite marquee (`#marquee-track`) with clone-based looping. They are initialized inside separate `DOMContentLoaded` listeners in `script.js`.

**Chatbot:** Calls Groq API (`llama-3.3-70b-versatile`) directly from the browser using a hardcoded API key. Chat history persists via `localStorage` (key: `medida_certa_chat_history`, capped at 20 messages). The chatbot does NOT confirm appointments — it redirects to WhatsApp/Instagram.

## Known Issues / TODO

- The Groq API key is exposed in client-side `script.js` and must be moved to a backend proxy before production.
- WhatsApp and Instagram contact links in `index.html` are placeholders and need real clinic data.
- Some styles remain inline in `index.html` and should be consolidated into `style.css`.
