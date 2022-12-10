---
title: "Vuejs Deepcopy"
date: 2022-05-23
draft: false
tags: ["vue"]
categories: [programming]
---

#### Mapping objects into new ones

##### Parent

```html
<child-component :passed-data="arrData"></child-component>
```

##### Child

```javascript
export default {
    props: {
        passedData: {
            type: Array,
            required: true
        }
    },
    data() {
        return {
            localData: this.projects.map(x => ({...x})),
        }
    }
}

```
