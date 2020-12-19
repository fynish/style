[Style](../README.md#fynish-style)

# Python: Overview

  - [Linting](#linting)
  - [File Organization](#file-organization)
    - General
    - Test Files

---
## Linting

Code should adhere to:
  - Pep8
  - Pylint
  - Flake8

Note that as part of our [all teams linting](../all_teams/all_teams_linting.md) we require the use of double quotes in addition to the above linting rules.

[_top of page_](#python-overview)

---
## File Organization

### General

Projects should not use a flat organizational structure, but should instead group things into logical subdirectories. 

### Test Files

Test files should be placed in the same directory as the files they are testing – *not in a separate "test" directory*. The test file names should should be the same as the file they are testing, but with `_test` appended to the end.
```
interest_handling
  - utilities
    - interest_calculations.py
    - interest_calculations_test.py
    - future_projections.py
    - future_projections_test.py
  - api
    - rest_hadlers.py
    - rest_hadlers_test.py
```

[_top of page_](#python-overview)

---
Copyright © 2020-2021. Released under a [MIT License](https://opensource.org/licenses/MIT).
