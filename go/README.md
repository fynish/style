[Style](../README.md#fynish-style)

# Go: Overview

Go doesn't give you as much leeway as some of the other languages we use. This section is perhaps even more WIP than the rest of our guide and will continue to evolve.

  - [File Organization](#file-organization)
    - General
    - Test Files

---
## File Organization

### General

It's common in go to have a flat organizational structure. We are fine with this if you are making a very small app/module. 

If you know in advance that your app will be larger, files should be separated into logical subdirectories *(while avoiding stutter)*. As your small app or module begins to grow, you should reorganize it into directories as soon as it makes sense to do so. *(Make sure you are moving your files in a way that preserves the git history.)*


[_top of page_](#go-overview)

---
### Test Files

Test files should be placed in the same directory as the files they are testing. The test file names should should be the same as the file they are testing, but with `_test` appended to the end.

```
▾ input_parse
  - ingest_user_input.go
  - ingest_user_input_test.go
  - filter_outliers.go
  - filter_outliers_test.go
▾ output_format
  - generate_response.go
  - generate_response_test.go
main.go
README.md
```

[_top of page_](#go-overview)

---
Copyright © 2020-2021. Released under a [MIT License](https://opensource.org/licenses/MIT).
