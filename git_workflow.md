# Git Workflow

**A brief overview of how our team uses git and github**

- [Starting New Issues](#starting-new-issues)
- [Branch Naming](#branch-naming)
- [PRs](#prs)
  - [Creating a PR](#creating-a-pr)
  - [CI Check](#ci-check)
  - [Asking for Review](#asking-for-review)
  - [Merging to Master](#merging-to-master)
    - [Squash Merging](#squash-merging)
    - [Rebase Merging](#rebase-merging)
- [How Strict Are The Rules](#how-strict-are-the-rules)

---
## Starting New Issues
When starting a new issue, assign it to yourself and mark the issue `WIP` (work-in-progress).

[_top of page_](#git-workflow)

---
## Branch Naming
The branch on which you are working should be named in the format `issue-[issue number]/title-of-issue`.
Add leading `0`s as needed to end up with four numbers. Example: `issue-0012/make-everything-shiny`

[_top of page_](#git-workflow)

---
## PRs

### Creating a PR:
PRs created before the code is ready for review should be tagged with `WIP` (work-in-progress), and then changed to `RFR` once ready for review. Your PR should have the same name as your issue. The description should contain one of github's trigger words (i.e. `closes` or `resolves`) if it closes the issue. 
```
Closes #1234 Add Stow-a-way Detector API
```

If it contributes to the issue, but more work is still needed to close the issue, it should just mention the issue without a trigger word. In this case, consider if the issue should be broken into separate issues.
```
Part of #5678 Some Overly Broad Issue Name
```

### CI Check:
CI will automatically run on your code as soon as you push it to github. All code must pass the CI checks before being merged. This will include running tests, linters, and code coverage checks. You will see individual green checks (or red Xs) indicating pass/fail for each CI criteria.

[_top of page_](#git-workflow)

---
### Merging to Master

Once your PR has passed all CI checks and has approval from a reviewer, it can be merged to Master via a **Squash & Merge** or by **Rebase Merge**. We only want useful commit messages left in our git history. Long commit messages (or too many commits) make future troubleshooting harder by adding noise to the git history. 

#### Squash Merging
When squashing via the github website, it will automatically add all your commits in an asterisks delimited list. You almost certainly want to delete all lines starting with `*` before merging. This is what github will do by default, **but do not let it**:
```
commit f1bba9ca8d7b14f42ac7
Author: Malcolm Reynolds <mreynolds@browncoat.tld>
Date:   Tue Nov 16 19:08:04 2021 

Add new InventoryLib to Interact with Radar (#1234)
* Get initial version working 

* Add better filtering.

* Fix tests

* Appease the linter

* This time it should all work.
```

This adds no benefit, makes it harder to interact with the history in a terminal, and makes it harder to debug things. We know your PR meets linting requirements and has tests. That's enforced by CI. Don't put it in a message that ends up in our final history. Instead, the above commit should look like this:

```
commit f1bba9ca8d7b14f42ac7
Author: Malcolm Reynolds <mreynolds@browncoat.tld>
Date:   Tue Nov 16 19:08:04 2021 

Add new InventoryLib to Interact with Radar (#1234)
```


If you do feel like you need a bunch of individual `* did a thing` messages, see Rebase Merging below.

#### Rebase Merging
**Only use the rebase merging method if it is helpful for ALL of your individual commits to be added to history.**

Your PRs should be small and easy to review. This typically lends itself to a single final commit. However, sometimes there are clear logic separations in the same PR. In these cases, it makes sense to leave the commits separate. This is an example of the end result of using a Rebase Merge to keep two separate commits from a single PR. The first commit is for the creation of a frontend service and the second commit contains the changes to components that use the service.
```

commit 015d1ab0ad42b2885f22
Author: Kaylee Fry <kfry@unpopularmechanics.tld>
Date:   Tue Nov 16 13:26:00 2021 

refactor: Update existing sensor implementations to also consume RadarLib

commit d082f79d7489a324a419
Author: Kaylee Fry <kfry@unpopularmechanics.tld>
Date:   Tue Nov 16 13:26:00 2021 

feat: Add new async RadarLib service 
```

[_top of page_](#git-workflow)

---
## How Strict Are The Rules
This is just general information about how we do things as a team. For anything we are not enforcing via CI rules (i.e. everything in this workflow), these are only our preferences. We are expecting you to make a reasonable, informed decision as to what is best for your specific scenario. You will have the most context into whatever issue you are working on. So, make good choices, and don't do dumb things.

[_top of page_](#git-workflow)