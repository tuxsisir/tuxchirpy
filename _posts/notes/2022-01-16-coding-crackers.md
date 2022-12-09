---
title: "Coding Crackers"
date: 2022-01-16
draft: false
tags: ["preps"]
---


### make_bricks

```python

def make_bricks(small, big, goal):
    big_can_be_used = goal // 5 # 2

    if (big_can_be_used > big):
      if (big * 5 + small >= goal):
        return True
    else:
      if (big_can_be_used * 5 + small >= goal):
        return True
    return False
```

https://codingbat.com/prob/p118406
