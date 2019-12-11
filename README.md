# vue-slim-stackedbar

A Simple horizontal stacked bar chart Component for Vue.

## Installing

```bash
$ npm install vue-slim-stackedbar
```

## Preview & Usage

<p align="center"><img align="center" style="width:600px" src="https://i.imgur.com/A0adjUh.png"/></p>

```js
<template>
  <div>
    <StackedBar :data="data"/>
  </div>
</template>

<script>
import StackedBar from 'vue-slim-stackedbar';

export default {
  components: {
    StackedBar,
  },
  data() {
    return {
      data: [
        { value: 19, },
        { title: 'Second', value: 36, },
        { text: '45%', title: 'Third', value: 45, },
      ],
    };
  },
};
</script>
```


## Author

**vue-slim-stackedbar** © [CHE5YA](https://github.com/che5ya), Released under the [MIT](./LICENSE) License.<br>

> GitHub [@che5ya](https://github.com/che5ya) · Facebook [@che5ya](https://www.facebook.com/che5ya) · Twitch [@chesya_](https://www.twitch.tv/chesya_)


## License

[MIT](LICENSE)
