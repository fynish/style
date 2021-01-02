[Style](../README.md#fynish-style) > [General](./README.md)

# Code Comments
 
As a general rule, we are very selective in our use of code comments. The code should generally speak for itself. If comments do exist:
1. They should **describe how it's consumed** and **not what the code does**.
2. Comments can include code if that is the best way to describe your message, but do not merge commented out blocks of code.
3. TODOs are permissible if they [pass linting](./all_teams_linting.md).

### Example Bad Comments

```javascript

// find the values over 1,000 in list of items
function highlightHighRangeItems(rsp) {
  const matches = [];
  // loop over results to find high range items
  rsp.forEach((item) => {
    if (item.value > 1000) {
      matches.push(item);
    }
  });
  // highlight the matched items
  updateItemList(matches);
}
```

### Example Acceptable Comments

```javascript

function FetchService(method, url, body = null) {
/*
    This service is used for DB interaction in lieu of directly consuming
    fetch(). It is the only place using fetch() directly is allowed.

    FetchService itself should only be called from the ApiLib service.
    No component should directly consume FetchService, but should instead
    use the appropriate ApiLib.
*/
```

    
[_top of page_](#code-comments)

---
Copyright © 2020-2021. Released under a [MIT License](https://opensource.org/licenses/MIT).
