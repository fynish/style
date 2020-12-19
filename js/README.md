[Style](../README.md)

# JavaScript - Overview

  - [Linting](#linting)
  - [File Organization](#file-organization)
    - General
    - Test Files
  - [Testing](#testing)

---
## Linting

Code should adhere to:
  - Eslint *(w/ Airbnb's Style)*

Note that as part of our [all teams linting](../all_teams_linting.md) we require the use of double quotes in addition to the above linting rules. JS does not care, but the default requirement from Airbnb's Eslint is single quotes. This will have to be overridden.

---
## File Organization

### General

Projects should not use a flat organizational structure, but should instead group things into logical subdirectories. 

### Test Files

Test files should be placed in the same directory as the files they are testing. The test file names should should be the same as the file they are testing, but with `_test` appended to the end.
```
interest_handling
  - utilities
    - interest_calculations.js
    - interest_calculations_test.js
    - future_projections.js
    - future_projections_test.js
  - api
    - rest_hadlers.js
    - rest_hadlers_test.js
```

---
## Testing

Test should use (Jest)[https://jestjs.io/].

---
Copyright © 2020-2021. Released under a [MIT License](https://opensource.org/licenses/MIT).
