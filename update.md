## Update personal website

### Source of truth
All CV content lives in `/Users/dschiava/Documents/02_Documents/10_CurriculumVitae/02_ModularCV/content/`.
**DO NOT EDIT ANY FILE IN THAT FOLDER. READ-ONLY.**

The relevant files and what they contain:

| File | Website section |
|---|---|
| `publications_submitted.tex` | Recent Preprints |
| `publications_peerreviewed.tex` | Peer-Reviewed Publications |
| `book_chapters.tex` | Book Chapters |
| `publications_confproceedings.tex` | Conference Proceedings |
| `publications_techreports.tex` | Technical Reports |
| `honors_awards.tex` | Honors & Awards |
| `funding_current.tex` | News (grants) |
| `funding_completed.tex` | News (grants, historical) |
| `funding_pending.tex` | News (pending grants, if awarded) |

---

### Standard update procedure

**Step 1 — Read the current site**
Read `index.html` in full to understand the current state before making any changes.

**Step 2 — Read the CV content folder**
Read all relevant `.tex` files listed above. Compare each section against what is currently in `index.html` to identify what is new.

**Step 3 — NEWS section**
- Add new entries for papers accepted/published, grants awarded, and notable events, in reverse chronological order (most recent first).
- Keep exactly **5 entries** visible as "current news" (blue left border: `border-blue-600`).
- Move all older entries into the collapsible "Older News" accordion (gray left border: `border-gray-400`).
- Date format: "Month YYYY" when the exact month is known, otherwise just "YYYY".
- Typical news entry HTML pattern:
  ```html
  <div class="card border-l-4 border-blue-600 pl-6">
      <p class="text-sm text-gray-500 mb-1">Month YYYY</p>
      <p>Description of the news item.</p>
  </div>
  ```

**Step 4 — HONORS & AWARDS section**
- Compare `honors_awards.tex` against the current `<section id="honors">`.
- Add any missing awards in reverse chronological order.
- Each entry is an `<li>` inside the `<ul class="space-y-4 border-l-2 border-blue-200 pl-4">`.

**Step 5 — PUBLICATIONS section**

*Recent Preprints* (always visible, not collapsible):
- Reflects `publications_submitted.tex`.
- Remove papers that have moved to peer-reviewed (i.e., they now appear in `publications_peerreviewed.tex`).
- Add new submitted papers at the top.
- Keep arXiv and GitHub links when available.
- Numbered list starting at `start="1"`.

*Peer-Reviewed Publications* (collapsible accordion):
- Reflects `publications_peerreviewed.tex`.
- Add new papers at the top of the list (most recent first).
- The list uses `start="5"` (since preprints occupy items 1–4).
- Each new peer-reviewed paper shifts all subsequent numbering down, so update the `start` attribute of subsequent sections accordingly (see numbering table below).

*Book Chapters* (collapsible accordion):
- Reflects `book_chapters.tex`.
- Update `start` attribute = 5 + (number of peer-reviewed items).

*Conference Proceedings* (collapsible accordion):
- Reflects `publications_confproceedings.tex`.
- Update `start` attribute = book chapters start + (number of book chapters).

*Technical Reports* (collapsible accordion):
- Reflects `publications_techreports.tex`.
- Update `start` attribute = conference proceedings start + (number of conference proceedings).

**Current numbering as of May 2026 update:**

| Section | start | # items | last item # |
|---|---|---|---|
| Recent Preprints | 1 | 4 | 4 |
| Peer-Reviewed | 5 | 45 | 49 |
| Book Chapters | 50 | 2 | 51 |
| Conference Proceedings | 52 | 4 | 55 |
| Technical Reports | 56 | 7 | 62 |

---

### Group section maintenance

**Current Graduate Students** (`<section id="group">`):
- A bulleted list with name, thesis topic.
- Update when students join or graduate.

**STRAND Undergraduate Students**:
- Sits between the current graduate students and the Alumni accordion.
- Shows one italic line with the shared project theme, then a single comma-separated line of student names.
- Update each academic year.
- HTML pattern:
  ```html
  <div class="mb-8">
      <h3 class="text-xl font-semibold text-gray-600 mb-1">STRAND Undergraduate Students</h3>
      <p class="text-sm text-gray-600 mb-3"><em>Project theme description</em></p>
      <p class="text-gray-700">Name 1, Name 2, Name 3</p>
  </div>
  ```

**Graduate Alumni** (inside collapsible accordion):
- Each entry has: name, date range (if known), thesis title, and a "Current position" line.
- Current position is initially set to "NA" and should be updated when known.
- HTML pattern:
  ```html
  <li>
      <strong>Full Name</strong> (Start - End)
      <p class="text-sm text-gray-600"><em>Thesis title</em></p>
      <p class="text-sm text-gray-500 mt-1">Current position: ...</p>
  </li>
  ```

**Undergraduate Alumni** (inside same accordion, right column):
- Each entry has: name, date range, project title, and optionally a paper link.

---

### Last update — May 2026

Changes applied in this session:

**NEWS:**
- Added 4 new current news items (2026 publications): Lagunowich et al. (JMLMC), Geraci et al. (SIAM JSC), Lee & Schiavazzi (CBM), Choi et al. (CBM).
- Moved Nov 2025 (BELS grant), Oct 2025 (SIAM MDS), Aug 2025 (Sandia), May 2025 (PTRS A) into Older News.
- NeurAM (Dec 2025) remains as the 5th current news item.

**HONORS & AWARDS:**
- Added: ICME Poster Award, ICME Expo 2016, Stanford University.

**PUBLICATIONS — Recent Preprints:**
- Removed 3 papers now published: Lee & Schiavazzi (arXiv 2510.20970 → CBM 2026), Choi et al. (arXiv 2506.11683 → CBM), Geraci et al. (arXiv 2506.08921 → SIAM JSC 2026).
- Added 3 new submitted papers: Dey et al. (model synthesis, 2026), Choi FalconBC (2026), Villatoro et al. (assessing performance, 2025).
- Kept: Sun et al. (arXiv 2506.06297, optimal patient allocation).

**PUBLICATIONS — Peer-Reviewed:**
- Added 4 new items at the top: Lagunowich et al. (JMLMC 2026), Lee & Schiavazzi (CBM 2026), Geraci et al. (SIAM JSC 2026), Choi et al. (CBM 2025).
- Updated section `start` numbers: Book Chapters 46→50, Conference Proceedings 48→52, Technical Reports 52→56.

**GROUP:**
- Added "Current position: NA" to all 6 PhD alumni entries (to be filled in).
- Added STRAND Undergraduate Students section between current students and alumni accordion.
