[Style](../README.md#fynish-style) > [General](./README.md)

# Linting
 
Teams should follow the linting rules decided for the language in which they work. In addition to those language-specific rules, all teams should also adopt the following rules and enforce them in CI.

  - [TODOs](#todos)
  - [Linter Updates](#linter-updates)

---
## TODOs

The use of TODO comments is allowed, but only if that comment has an issue number that corresponds to your team's ticketing system.

**Passes Linting:**
```
// TODO: [#2345] This uses a slow API. When the new API is finished, switch to that.
```

**Fails Linting:**
```
// TODO: This uses a slow API. When the new API is finished, switch to that.
```
    
[_top of page_](#linting)

---
## Linter Updates

Periodically, a linter version update will render hundreds of lines of previously passing code with linting warnings/errors. For any new linting rule changes that can be resolved with an auto-fix, do not tie those changes to a human contributor. It is easier to understand the intent of the line change with git blame if you have [PedantBot](https://github.com/PedantBot) make the changes for you.

[_top of page_](#linting)

---
Copyright © 2020-2021. Released under a [MIT License](https://opensource.org/licenses/MIT).
