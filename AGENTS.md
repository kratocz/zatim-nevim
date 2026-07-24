# AGENTS.md

Guidance for AI coding agents working in this repository (Claude Code, Cursor, Aider, Copilot, …).

## Project overview

A public, from-scratch, course-style set of notes on learning **vim / neovim / LazyVim**,
written in Czech. This is **not** a software project and **not** an official vim course;
it's a growing notebook of lessons, a cheatsheet, progress tracking, and practice files. The repo name *„zatím nevím"*
is a Czech pun on *„I don't know yet"* with *vim* hidden inside.

## Struktura

- `README.md` — rozcestník, index Tracku A a vysvětlení účelu.
- `ROADMAP.md` — plán tří tracků (A od nuly, B přechod z IDE, C recepty) se stavem lekcí (✅/🚧/🔜).
- `progress.md` — tracker postupu (checkboxy po lekcích a tracích).
- `cheatsheet.md` — gramatika vim (módy, operátory, pohyby, text objekty, dávkové triky).
- `lekce/NN-nazev.md` — Track A: lineární kurz od nuly, číslované lekce.
- `prechod-z-ide/NN-nazev.md` — Track B: goal-oriented lekce pro lidi z VS Code / JetBrains (má vlastní README s indexem).
- `cviceni/*.txt` — cvičné soubory k procvičování zásahů (bezpečné hřiště).

## Setup / build / test

N/A — je to repo s poznámkami, nic se nebuilduje ani netestuje.

## Conventions

- **Jazyk obsahu:** čeština (lekce, cvičení, poznámky). Výjimka: horní disclaimer v `README.md`
  a tento „Project overview" jsou anglicky, aby cizinci pochopili účel a nespletli si repo
  s oficiálním zdrojem.
- **Lekce i cvičení číslovat** `NN-nazev` (`01-preziti`, `06-hledani-a-nahrazovani`, …) kvůli řazení; Track B čísluje uvnitř `prechod-z-ide/` od `00`.
- **Goal-oriented styl Tracků B/C:** lekce odpovídá na reálný dotaz „jak ve vim udělám X, co znám z IDE" — držet rozhodovací tabulky a recepty.
- **Cvičné soubory neničit nevratně** — originály jsou v gitu, k obnovení `git checkout <soubor>`.
- Nové lekce přidávat postupně, tempo drží uživatel. **Při přidání lekce aktualizovat:** `ROADMAP.md` (stav), příslušný index (README / track README), `progress.md` a odkaz „Co dál" v předchozí lekci.
