1. Which issues were the easiest to fix, and which were the hardest? Why?

answer :
The easiest issues to fix were missing docstrings and non–snake_case function names, since they mainly involved adding comments and renaming functions according to Python style guidelines (PEP 8).

The hardest issue was the bare except handling, because it required understanding which specific exceptions to catch and ensuring proper re-raising using raise ... from exc without breaking existing logic. The mutable default argument was also tricky since it needed refactoring function definitions to avoid unintended data sharing.

2. Did the static analysis tools report any false positives? If so, describe one example.

answer:
Yes, there was one false positive from Pylint related to the raise-missing-from warning.
Even though the error handling was properly implemented, Pylint still flagged it as a suggestion to chain exceptions using raise ... from exc. It wasn’t an actual bug but rather a stylistic recommendation.

3. How would you integrate static analysis tools into your actual software development workflow?

answer:
I would integrate tools like Pylint, Flake8, and Bandit into the Continuous Integration (CI) pipeline (for example, GitHub Actions).

Every time code is pushed or a pull request is made, the CI pipeline would automatically run these tools to catch style issues, bugs, and security flaws early.

During local development, I’d set up a pre-commit hook to run quick lint checks before committing, ensuring code quality is maintained consistently.

4. What tangible improvements did you observe in the code quality, readability, or potential robustness after applying the fixes?

answer:
The code became cleaner, more readable, and maintainable — with proper docstrings, consistent naming, and safe exception handling.

Using context managers for file operations reduced the risk of file leaks.

Removing the mutable default arguments prevented unexpected data persistence across function calls.

Overall, the program became more robust and professional, aligning with best coding practices and security standards.