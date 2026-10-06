\# Plan for Issue #69: Top-level JSON array fallback



\## Diagnosis



I reproduced the reported failure with a valid top-level JSON array. `parse\_review\_output()` successfully parses the raw JSON with `json.loads()` and passes the resulting list to `\_parse\_json\_output()`. `\_parse\_json\_output()` currently assumes the parsed value is a dictionary and iterates with `data.items()`. Because a top-level JSON array is parsed as a Python list, this path raises `AttributeError: 'list' object has no attribute 'items'`.



Reproduction evidence: running `python -m pytest .\\tests\\unit\\test\_output\_parser.py::TestOutputParser::test\_json\_array\_fallback -vv --runxfail` failed at `rag\\generator\\output\_parser.py:68` with `AttributeError: 'list' object has no attribute 'items'`.



\## Scope



In scope:

\- Update the JSON parsing path so a valid top-level JSON array does not cause `\_parse\_json\_output()` to call `.items()` on a list.

\- Keep the existing behavior for JSON objects and plaintext fallback intact.

\- Update the existing regression coverage for `test\_json\_array\_fallback` so the fixed behavior is verified.



Out of scope:

\- Refactoring unrelated parser behavior.

\- Changing the `FeedbackSection` model or unrelated JSON-object parsing.

\- Changing other seeded defects or unrelated tests in the repository.



\## Files



\- `rag/generator/output\_parser.py` — adjust the JSON parsing path to handle a parsed top-level list without calling `.items()` on it.

\- `tests/unit/test\_output\_parser.py` — update the existing `test\_json\_array\_fallback` regression test to verify the corrected behavior.



\## Approach



1\. Add explicit handling for a parsed JSON value that is a list before the existing dictionary `.items()` path is used.

2\. Convert the top-level array into valid `FeedbackSection` output without changing the existing handling for dictionary-shaped JSON.

3\. Update the existing array regression test so it is no longer an expected failure and asserts the observable fixed behavior.

4\. Keep the change focused on issue #69 and avoid modifying unrelated parser behavior.



\## Test plan



1\. Rerun the original reproduction command:

&#x20;  `python -m pytest .\\tests\\unit\\test\_output\_parser.py::TestOutputParser::test\_json\_array\_fallback -vv --runxfail`

2\. Before the fix, this command reproduces `AttributeError: 'list' object has no attribute 'items'`.

3\. After the fix, the top-level JSON array should be handled without raising that exception and the regression test should pass.

4\. Run the full `tests/unit/test\_output\_parser.py` test file to check that existing JSON-object and plaintext parsing behavior still passes.



\## Risks and unknowns



\- The reproduction confirms that a top-level JSON array reaches `\_parse\_json\_output()` and crashes on `.items()`, but the exact representation of each array item as a `FeedbackSection` still needs to be verified during implementation.

\- The fix should preserve current dictionary JSON behavior, so the existing parser tests need to be rerun after the change.

\- If implementation reveals repository conventions for array handling that are not apparent from the current parser and tests, the approach may need to be adjusted and recorded under Deviations.



\## Deviations



Nothing changed from the plan yet. Any implementation differences discovered while building the fix will be recorded here.



\## Deviations



The implementation used the existing plaintext fallback for top-level JSON arrays instead of creating a new per-item `FeedbackSection` representation. This avoided inventing new array semantics while fixing the reproduced crash. I also applied the same handling to both raw and fenced JSON paths, as described in the posted plan comment.

