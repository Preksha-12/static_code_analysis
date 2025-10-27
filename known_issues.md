# Known Issues

| Issue | Type | Line(s) | Description | Fix Approach | Status |
|---|---:|---:|---|---|---|
| Use of `eval()` | Security (High/Medium) | 59 | `eval()` executes arbitrary code — security risk. | Remove `eval()` and replace with safe logging or explicit calls. | Open |
| Bare `except:` | Reliability (Medium) | 19 | Bare except hides errors; impossible to debug. | Catch specific exceptions (e.g., `KeyError`) and log/re-raise as needed. | Open |
| Mutable default arg `logs=[]` | Bug (Medium) | 8 | Mutable default shared between calls causes state leakage. | Change default to `None`, initialize inside function. | Open |
| File open without `with` and no encoding | Reliability (Medium) | 26, 32 | Risk of file descriptor leak and encoding issues. | Use `with open(..., encoding='utf-8')` and `json.load/json.dump`. | Open |
| getQty missing validation (KeyError risk) | Reliability (Medium) | 22 | Accessing missing key will raise KeyError unexpectedly. | Validate input; raise descriptive error or return 0. | Open |
| Unused `logging` import | Style (Low) | 2 | `logging` imported but unused. | Use logging in code or remove import. | Open |
| Non-snake_case function names | Style (Low) | many | Functions are camelCase (e.g., addItem) not snake_case. | Rename to snake_case (`add_item`) and update calls. | Open |
| Missing docstrings | Maintainability (Low) | many | No docstrings for module/functions. | Add concise docstrings. | Open |
