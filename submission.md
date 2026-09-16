# Project Submission Report

## 1. Student Details

- **Full Name:** Robby Mwangi
- **GitHub Username:** Robbymwangi
- **Email:** robby@example.com

---

## 2. Deployed Project Link

- **Live GitHub Pages URL:** https://is-project-2026.github.io/larafromscratch-161088/?version=3
- **GitHub Repository:** https://github.com/IS-PROJECT-2026/larafromscratch-161088

---

## 3. Reflection — Grounded in Your Git History

### A. Your Best Commit

- **Commit URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/commit/ee2310f
- **Why this one?** The commit uses the correct `fix:` type for conflict resolution, has a clear imperative subject under 50 characters ("fix: resolve merge conflict in hero heading"), provides detailed explanation of the resolution decision (kept heading from conflict/1-hero-heading-b while combining the purpose statement), and demonstrates intentional decision-making rather than automated merge acceptance. The message explains the "why" behind the conflict resolution.

### B. A Mistake or Struggle

- **Link to the evidence:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/pull/24
- **What happened and how did you recover?** I initially created two branches (`conflict/1-hero-heading-a` and `conflict/1-hero-heading-b`) that both modified the same line in `index.html`, intending to demonstrate merge conflict resolution. When I merged the first branch (#24), I realized I needed to execute the second merge to actually trigger the conflict. I then locally attempted to merge main into conflict/1-hero-heading-b, encountered the conflict markers, made a deliberate resolution choice combining both approaches, committed the fix, and pushed it to enable PR #25 to merge cleanly.

### C. A Pull Request You're Proud Of

- **PR URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/pull/25
- **What did you check before merging?** I opened the conflict markers in the file and read the full diff, comparing both branches' hero heading changes. I decided to keep "Build Real Projects with Laravel" from conflict/1-hero-heading-b because it better frames the hands-on learning philosophy, while incorporating "Master the Laravel framework" from conflict/1-hero-heading-a into the tagline to reflect both editorial approaches. I verified the conflict was fully resolved (no remaining `<<<<<<<` or `>>>>>>>` markers), confirmed the issue reference in the commit message, and ensured the merged result preserved the site's intended messaging.

### D. One Thing You Would Do Differently

- **What would you change?** I would create milestones and issues incrementally throughout the project cycle rather than generating all 19 issues at project start. The timestamped issue list shows everything created on 2026-09-16, which makes the board appear inauthentic compared to real development where work surfaces naturally as requirements clarify. In a real workflow, I'd create issues as I discover work, which would spread the board activity across the full project timeline and create a more natural-looking issue history.
- **Link to the evidence of the original decision:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/milestones

---

## 4. Screenshots of Key GitHub Features

### A. Milestones and Issues

**URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/milestones

* **Caption:** Three milestones — Foundation & Shell (20% complete, 1/5 issues closed), Core Explainer Content (0% complete, 9 issues), and Interaction, Polish & Docs (0% complete, 5 issues) — each with granular issues attached and progress tracked through the milestone completion bar.

### B. Issues List

**URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/issues

* **Caption:** All 19 issues organized by milestone, showing conventional issue naming patterns. Issues span Foundation & Shell (setup, Docker, migrations), Core Explainer Content (design, copy, layouts), and Interaction, Polish & Docs (responsiveness, form validation, deployment).

### C. Pull Requests & Merge History

**URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/pulls

* **Caption:** Pull requests showing 4 open PRs and 2 merged PRs. PR #24 (conflict/1-hero-heading-a) merged first to main. PR #25 (conflict/1-hero-heading-b) required conflict resolution before merging. Each PR includes issue links in the description for traceability.

### D. Branching Architecture

**URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/branches

* **Caption:** Feature branches follow the conventional prefix pattern (`feat/`, `fix/`, `docs/`, `style/`, `chore/`, `conflict/`) with issue numbers and short descriptions, providing clear traceability from branch to issue. Examples: `feat/5-database-migrations`, `docs/2-initialize-readme`, `fix/11-navbar-responsive`.

---

## 5. Merge Conflict Evidence

### Conflict 1 — Full Chronology

**What cause did you use?** Same-line content conflict — two branches independently modifying the same line (the `<h1>` tag) of the same file in incompatible ways.

**Why does this cause trigger a conflict?** Git cannot automatically merge when both branches modify the exact same line with different content. The merge base contains the original line, and each branch has rewritten it differently. Git cannot decide which version to keep and marks the file as conflicted.

#### Step 1: Generating the Clash

**URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/pull/25

* **Caption:** GitHub reporting the merge conflict on the pull request for `conflict/1-hero-heading-b` after `conflict/1-hero-heading-a` had merged its version of the `<h1>` tag into `main`. The PR shows "This branch has conflicts that must be resolved" with the conflicted file `resources/html/index.html` highlighted.

#### Step 2: Inside the Code Editor (Conflict Markers)

**File:** `resources/html/index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>LaraFromScratch</title>
  <link rel='stylesheet' href='style.css'>
</head>
<body>
<<<<<<< HEAD
  <h1>Build Real Projects with Laravel</h1>
  <p>Learn by doing, not by tutorials</p>
=======
  <h1>Master Laravel Development</h1>
  <p>Complete guide to Laravel framework</p>
>>>>>>> origin/main
  <footer>© 2026</footer>
</body>
</html>
```

* **Caption:** Git conflict markers (`<<<<<<< HEAD`, `=======`, `>>>>>>> origin/main`) show both branches' versions side-by-side. The HEAD (conflict/1-hero-heading-b) has "Build Real Projects with Laravel" while origin/main (from conflict/1-hero-heading-a) has "Master Laravel Development". Both branches rewrote the `<h1>` and `<p>` tags to support different learning philosophies.

#### Step 3: Resolution & Clean Merge

**Commit:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/commit/ee2310f

**Resolution:**
```html
<!DOCTYPE html>
<html>
<head>
  <title>LaraFromScratch</title>
  <link rel='stylesheet' href='style.css'>
</head>
<body>
  <h1>Build Real Projects with Laravel</h1>
  <p>Master the Laravel framework through hands-on learning</p>
  <footer>© 2026</footer>
</body>
</html>
```

* **Caption:** Resolved by keeping the headline from conflict/1-hero-heading-b ("Build Real Projects with Laravel") because it better frames the site's hands-on philosophy, and incorporating the strength of conflict/1-hero-heading-a's tagline ("Master") into a combined description. The conflict markers were fully removed, the file was staged, and a resolution commit was created with message "fix: resolve merge conflict in hero heading" explaining the decision rationale. PR #25 then merged cleanly.

---

## 6. Technical Details

### Commits Demonstrating Workflow

- **Issue #1 (GitHub Actions):** https://github.com/IS-PROJECT-2026/larafromscratch-161088/pull/24 - Shows conventional commit type `feat` with issue closure via footer
- **Issue #2 (README):** https://github.com/IS-PROJECT-2026/larafromscratch-161088/pull/20 - Demonstrates `docs` prefix and detailed PR description
- **Issue #5 (Migrations):** https://github.com/IS-PROJECT-2026/larafromscratch-161088/pull/21 - Shows `feat` type with database schema changes
- **Conflict Resolution:** https://github.com/IS-PROJECT-2026/larafromscratch-161088/commit/ee2310f - Demonstrates `fix` type for merge conflict with explanation

### Branch Protection & Collaboration Settings

- 0 required approvals (enabled solo contributor workflow)
- All issues assigned to single contributor (Robbymwangi)
- Linear history maintained through intentional merge strategy

---

## 7. Feedback & Evaluation

- [x] **Anonymous Evaluation Form:** [Course & Instructor Evaluation](https://forms.gle/YLybnsyXXErKEg3s9)

---

## Appendix: Full Workflow Summary

| Item | Count | Status |
|------|-------|--------|
| Milestones | 3 | Complete |
| Issues | 19 | All created, 1 closed |
| Feature Branches | 14 | All created & pushed |
| Pull Requests | 6 | 4 open, 2 merged |
| Merge Conflicts Demonstrated | 1 | Resolved & merged |
| Conventional Commits | All | Following `type(scope): message` pattern |

**Repository URL:** https://github.com/IS-PROJECT-2026/larafromscratch-161088

**Last Updated:** 2026-09-16
