# WLAN Report Handoff

## Goal and scope

Maintain the Vietnamese LaTeX report for the Group 9 computer-networks WLAN project. Use the supplied reference PDFs for WLAN theory only. Keep experimental configuration, measurements, screenshots, and results as empty report sections for the student team to complete.

## User constraints

- Write the report in Vietnamese while preserving established academic tone and tables.
- Keep standard names and specialist English terms beside Vietnamese wording on first use; retain protocol names, acronyms, equations, and standards accurately.
- Keep six member-name fields blank on the cover. Do not copy personal information from the reference reports.
- The cover is a reusable source file included from `main.tex`; do not replace it with a PDF page.
- The user explicitly asked to skip MiKTeX compilation. Do not install or run MiKTeX unless the user later asks.
- Do not overwrite or regenerate `main.pdf` without explicit approval. It is already modified in the working tree.

## Files

- `main.tex`: document order, abstract, and intentionally empty experiment headings.
- `cover.tex`: reusable Group 9 cover template with six blank member lines.
- `sections/01_introduction.tex`: WLAN overview, LAN vs WLAN comparison, wireless classification.
- `sections/02_standards_spectrum.tex`: IEEE 802.11 generations, bands, channels, and regulation (verified Circular 01/2025/TT-BKHCN / 08/2021/TT-BTTTT).
- `sections/03_architecture.tex`: WLAN components, topologies, Infrastructure vs Ad-hoc comparison, MANET/Wi-Fi Direct, WDS 4-address framing, Split-MAC / CAPWAP, OSI placement, and supporting services (Windows, Android, iOS clients).
- `sections/04_security.tex`: WLAN security evolution, localized 4-way handshake TikZ diagram, WPA3/SAE/OWE, enterprise authentication, threats, and hardening.
- `sections/A_abbreviations.tex`, `sections/B_terminology.tex`: acronym list and fully translated English–Vietnamese terminology table (100% Vietnamese definitions).
- `references.bib`: standards, research, student-report references, and newly added literature (Kurose & Ross 6th ed., Cisco, Cisco Press, Wi-Fi Alliance, Microsoft, Google, Apple).
- `tham_khao/main (2).pdf`: 74-page WLAN theory/project report (Nhóm 06). Theoretical foundation referenced for architecture and comparison.
- `tham_khao/Report (1).pdf`: 31-page office-network report (Nhóm 31). Referenced for hierarchical network integration theory.

## Suggested agent team

Use one lead agent to own integration and prevent overlapping edits. Delegate bounded tasks with disjoint file scopes:

- **Theory researcher:** inspect the WLAN reference PDF; recommend theory additions or corrections for `sections/01_introduction.tex` and `sections/02_standards_spectrum.tex` only.
- **Architecture/security researcher:** review theory coverage and terminology in `sections/03_architecture.tex` and `sections/04_security.tex` only.
- **Vietnamese/editorial reviewer:** inspect `sections/A_abbreviations.tex` and `sections/B_terminology.tex`; report untranslated prose, terminology inconsistency, and table issues. Coordinate before changing files owned by another agent.
- **Integration/build reviewer:** review citations, cross-references, LaTeX structure, and diff. Do not compile unless the user authorizes it and a compiler is available.

## Handoff protocol

Before delegating, give each agent a read/write scope and ask it not to touch other files. Require each handoff to list files inspected or changed, findings, checks performed, and unresolved issues. The lead agent integrates changes, resolves conflicts, checks citation keys and cross-references, and runs `git diff --check`. Do not treat the existing `main.pdf` as a fresh build.

## Current status (updated 2026-10-30)

- **A4 & pagination:** `preamble.tex` now configures A4 with readable margins. The contents, figures/tables lists, references, contribution table, and each appendix begin on a fresh page where applicable.
- **Cover:** `cover.tex` has a six-row blank member table; no personal details were copied from source PDFs.
- **Requested structure:** `main.tex` includes connection guidance, generic router/device configuration, evidence placeholders, experiment/result placeholders, conclusion, references, contribution/signature table, and separate abbreviation/terminology appendices.
- **Acceptance tracking:** `CHECKLIST.md` records all 13 requested structure items and the 14 acceptance points in `KeHoach/phancong.pdf`. It distinguishes section presence from actual completion and notes the PDF's five-member roster versus the user's six blank slots.
- **Build/visual check:** Not performed. User instructed to skip MiKTeX; `main.pdf` remains untouched and is not evidence of the current LaTeX source.

- **Cover & Structure:** A reusable cover is included by `main.tex`; it retains six blank member lines and instructor line. Headings under `\section{Thực nghiệm}` in `main.tex` remain intentionally empty for the student team.
- **Terminology Appendix (`sections/B_terminology.tex`):** 100% of explanatory definitions (column 3) across all 5 categories have been translated into academic Vietnamese. Table continuation headers have been localized. Columns 1 and 2 remain intact.
- **Security Section (`sections/04_security.tex`):** TikZ 4-way handshake diagram labels fully localized to Vietnamese (`dẫn xuất PTK, kiểm tra MIC`, `kiểm tra MIC, cài đặt PTK/GTK`, `thông số bảo mật`, `yêu cầu cài đặt khóa`). Citations to `wpa3_overview` and `wpa3_deployment` added.
- **Architecture Section (`sections/03_architecture.tex`):** Substantially enhanced with:
  - Ad-hoc architecture variants: Single-hop, Multi-hop MANET (AODV/DSR/OLSR routing), and Wi-Fi Direct (P2P Group Owner / Client).
  - WDS 4-address MAC frame format (To DS=1, From DS=1, RA/TA/DA/SA fields).
  - Split-MAC architecture: Real-time MAC (AP) vs Non-real-time MAC (WLC) via CAPWAP DTLS.
  - Comprehensive comparison table: Infrastructure Mode vs Ad-hoc Mode.
  - End devices integration (Windows, Android, iOS).
  - Synchronized `tomtat` summary block.
- **Spectrum & Regulation (`sections/02_standards_spectrum.tex`):** Regulatory claims regarding Circular 01/2025/TT-BKHCN (amending Circular 08/2021/TT-BTTTT) allocating 5925–6425 MHz for Wi-Fi in Vietnam effective May 15, 2025 have been verified against official legal documents. Citation `cisco_rf_guide` added for RF channels.
- **Bibliography (`references.bib`):** Enriched with all references requested by member assignments: `kurose2012`, `cisco_intro_80211`, `ciscopress_topologies`, `cisco_rf_guide`, `wpa3_overview`, `wpa3_deployment`, `microsoft_wifi`, `google_android_wifi`, `apple_ios_wifi`.
- **Validation:** `git diff --check` passed cleanly with code 0.
- **Unverified items & Remaining risks:**
  - Compilation was strictly skipped per user requirement; `main.pdf` in the working tree does not yet reflect the latest LaTeX modifications.
  - Individual experimental measurements and screenshots must be filled in by the student team in `\section{Thực nghiệm}`.
