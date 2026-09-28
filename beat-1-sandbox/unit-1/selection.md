# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

[https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69)

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69",
    "checks": [
      {"name": "open_and_unassigned", "grade": "pass", "evidence": "Issue metadata: state=OPEN, assignees=0"},
      {"name": "no_linked_pr", "grade": "pass", "evidence": "No open/merged PR in codepath/pathreview-ai301-fa26-s1 references #69 or touches rag/generator/output_parser.py; thread mentions no PR"},
      {"name": "recent_repo_activity", "grade": "pass", "evidence": "Last default-branch commit 2026-09-16T21:48:26Z, 11 days before today (2026-09-27)"},
      {"name": "clear_scope", "grade": "pass", "evidence": "Body names rag/generator/output_parser.py, the exact AttributeError on .items(), and the H-02 xfail marker to remove"},
      {"name": "newcomer_accessible", "grade": "pass", "evidence": "jacho15 repro: 'installed just the two deps this test file actually needs (pip install structlog pytest)' — no API key or Docker"},
      {"name": "maintainer_responsive", "grade": "pass", "evidence": "Aburke225 [COLLABORATOR] commented on repo issues 2026-09-16, within 60 days"}
    ],
    "verdict": "accept"
  },
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

- Run 1: 0/20 agreement (error: empty checks / Claude CLI non-zero exit code due to authentication).
- Run 2: 18/20 agreement (PASS - met category floor criteria and generated official `eval-run.txt`).

**Issue analysis**

- **Issue ID:** `issue-19`
- **Rubric Verdict:** `reject`
- **Gold Verdict:** `accept`
- **Reasoning:** My rubric evaluated `issue-19` as a `reject` because it failed the `clear_scope` check. The issue description left open architectural decisions regarding fallback logic, which my rubric interpreted as lacking clear scope, whereas the gold label deemed it manageable for a newcomer.

**Check rationale**

> `| open_and_unassigned | Issue state field and assignee list from issue metadata | State is OPEN and zero assignees are assigned to the issue | required |`

Reasoning: First-time contributors often get discouraged when attempting to work on issues that are already claimed or closed. Setting this check as `required` prevents duplicate effort and ensures the candidate issue is available to be claimed.

**Trade-offs**

Requiring explicit file paths and zero architectural ambiguity in `clear_scope` protects new contributors from getting stuck on underspecified bugs. However, this strictness trade-off risks rejecting valid, beginner-friendly issues that simply require minor investigation before fixing.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
Issue #69 fits my available time well as a focused bug fix in the RAG module without requiring broad system setup.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
The verdict correctly verified that Issue #69 is open, unassigned, has clear scope, and has no open PRs. Beyond the rubric, I weighed that fixing an explicit `AttributeError` with unit test repro steps is straightforward to test locally.
3. The anticipated difficulty in claiming it.]
    Low difficulty, as the issue is open, unassigned, and provides specific reproduction steps and target file locations.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
