# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

Tommy1070

**Plan comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69#issuecomment-6021253855

**Plan comment exact text**

I reproduced #69 and traced the failure to the JSON parsing path. A valid top-level JSON array is successfully parsed by `json.loads()`, but `_parse_json_output()` currently assumes the result is a dictionary and calls `.items()`, which raises `AttributeError` when the parsed value is a list.

My plan is to add explicit handling for top-level JSON arrays while preserving the existing dictionary and plaintext behavior. I’ll account for both raw JSON and fenced JSON paths that can reach `_parse_json_output()`. I’ll also update the existing `test_json_array_fallback` regression coverage and remove its `xfail` marker as part of the fix.

For validation, I’ll rerun the original reproduction and the full `tests/unit/test_output_parser.py` test file. The reproduction confirms the `.items()` failure, but I’ll verify the appropriate `FeedbackSection` representation for array items during implementation rather than assuming it in advance.

---

## Your branch

**Branch**

fix/69-json-array-fallback

**Evidence**

Before:

Command:

`python -m pytest .\tests\unit\test_output_parser.py::TestOutputParser::test_json_array_fallback -vv --runxfail`

Output:

`AttributeError: 'list' object has no attribute 'items'`

The failure occurred in `rag\generator\output_parser.py:68` when `_parse_json_output()` called `data.items()` on the parsed top-level JSON array.

After:

Command:

`python -m pytest .\tests\unit\test_output_parser.py::TestOutputParser::test_json_array_fallback -vv`

Output:

`1 passed in 0.45s`

Full parser regression run:

Command:

`python -m pytest .\tests\unit\test_output_parser.py -vv`

Output:

`19 passed in 0.23s`

## Eval iterations

**Run history**

`18/20`

The full evaluation run produced:

`agreement: 18/20 scored items  (bar: 18/20: PASS)`

**Package analysis**

`pkg-05`

My rubric decided: `reject`

Gold label: `accept`

The evaluation reported:

`failed: Risks and unknowns are honest`

My check requires unresolved assumptions to be labeled as unknowns and their impact explained. The package was otherwise a clear-accept example, but my rubric read its treatment of risks and unknowns as insufficiently explicit, so it rejected the package while the gold label accepted it.

**Check rationale**

Check from my uploaded `rubric.md`:

`Risks and unknowns are honest`

Evidence:

`risks/unknowns vs repro and repo facts.`

Pass condition:

`unresolved assumptions labeled unknown, impact explained.`

I kept this check because a plan should distinguish reproduced facts from implementation assumptions. During my own issue #69 plan, I knew the reproduction proved the `.items()` crash, but it did not prove the correct `FeedbackSection` representation for each array item. Requiring that uncertainty to be stated prevents a plan from presenting an unverified implementation choice as confirmed behavior.

**Trade-offs**

The stricter risks-and-unknowns check changed the result for `pkg-05`: the gold label was `accept`, while my rubric returned `reject`. I accept that trade-off because the check intentionally requires plans to make unresolved implementation assumptions explicit. The final evaluation still reached `18/20`, and every evaluation category had at least one matching result.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.