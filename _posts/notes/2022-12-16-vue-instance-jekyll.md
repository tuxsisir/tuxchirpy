---
title: Vue instance in jekyll
date: 2022-12-16
tags: ["vue"]
pin: true
category: programming
---

### Intro

In this post, we'll go through how to embed and use vue from cdn in jekyll post. It's pretty straightforward to implement.
The only thing that we need to make sure is that we don't mix jekyll's moustache {% raw %}`{{ }}`{% endraw %} syntax collide with vue.

There are two ways achieve this:
1. Either make use of `{% raw %} {% raw %}... {% end raw %}{% endraw %}` within your content.
2. Or, by adding `delimeter` options in your vue instance.


#### The result below is being rendered by adding `delimeter` in **Vue** instance

---
<div id="app">
  [[ message ]]
  <button name="button" v-on:click="counter++">Counter: [[ counter ]]</button>
</div>

---

#### Add this portion of div with id="app" in your markdown content
```html
<div id="app">
  [[ message ]]
  <button name="button" v-on:click="counter++">Counter: [[ counter ]] </button>
</div>
```

#### Include this at the end of your markdown
```vue
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: "#app",
    delimiters: ['[[', ']]'], // changes your delimeter to [[ ]]
    data: {
      counter: 0,
      message: "Hello World from Vue! 🔮",
    },
  });
</script>
```

That's all to implement Vue in your jekyll post and make your content more interesting and interactive.
Thanks for reading!

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: "#app",
    delimiters: ['[[', ']]'],
    data: {
      counter: 0,
      message: "Hello World from Vue! 🔮",
    },
    methods: {
      increaseCounter() {
        this.counter++
      }
    }
  });
</script>

