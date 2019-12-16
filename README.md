# vue-slim-stackedbar

A Simple horizontal stacked bar chart Component for Vue.

## Installing

```bash
$ npm install vue-slim-stackedbar
```

## Preview & Usage

* Preview Image
<p align="center"><img align="center" style="width:600px" src="https://i.imgur.com/A0adjUh.png"/></p>

* Default Usage
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
        { title: 'First', value: 19 },
        { title: 'Second', value: 36 },
        { title: 'Third', value: 45 },
      ],
    };
  },
};
</script>

```

* If you wanna use custom colors, then :
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
        { title: 'First', value: 19, color:'#dc3545' },
        { title: 'Second', value: 36, color:'#6610f2' },
        { title: 'Third', value: 45, color:'#ffc107' },
      ],
    };
  },
};
</script>

```

## Props

| Name    | Type     | Default   | Description                                                                                    |
|--------------------|-----------|----------------------|-------------------------------------------------------------------------|
| title   | String   | -         | Title of Data Stack. Only **String** can be used.                                              |
| value   | Number   | -         | Value of Data Stack. Only **Number** can be used. The sum of the data must not exceed **100**. |
| color   | String   | -         | Background Color of Data Stack. Only **Color HexCode** can be used. If you do not use Color String, One of **15 random colors** will be inserted automatically. |


## Author

**vue-slim-stackedbar** © [CHE5YA](https://github.com/che5ya), Released under the [MIT](./LICENSE) License.<br>

> GitHub [@che5ya](https://github.com/che5ya) · Facebook [@che5ya](https://www.facebook.com/che5ya) · Twitch [@chesya_](https://www.twitch.tv/chesya_)


## License

[MIT](LICENSE)
