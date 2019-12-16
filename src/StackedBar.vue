<template>
  <div class="wrap__stack">
    <div
    class="item__stack"
    v-for="(item, index) in data"
    :key="index"
    :style="bgColor(item, index)+'flex-basis:' + item.value +'%;'"
    data-color="">
      <div class="label__stack">
        <i class="decoration__stack" />
        <span
        class="text__stack"
        v-if="item.title">
          {{item.title}}: <strong>{{item.value}}</strong>
        </span>
        <span
        class="text__stack"
        v-else>
          <strong>{{item.value}}</strong>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import HexToRGB from 'hex-to-rgb';

export default {
  name: 'StackedProgressBar',
  props: {
    data: {
      type: Array,
      default: null,
    },
  },
  data() {
    return {
      colors: [
        '#007bff', '#6610f2', '#6f42c1', '#e83e8c', '#dc3545',
        '#fd7e14', '#ffc107', '#28a745', '#20c997', '#17a2b8',
        '#516f7d', '#343a40', '#ff5a46', '#989486', '#f28b8c',
      ],
    };
  },
  methods: {
    bgColor(item) {
      if (item.color) {
        const colorArray = (item.color).split('#');
        const color = HexToRGB(colorArray[1]);
        return `background-color:rgba(${color[0]}, ${color[1]}, ${color[2]}, 1);`;
      }
      const randomChoice = this.colors[Math.floor(Math.random() * this.colors.length)];
      return `background-color:${randomChoice};`;
    },
  },
};
</script>

<style scoped>
.wrap__stack {
  display: flex;
  border-width: 1px;
  border-style: solid;
  border-color: #EEE;
  background-color: #ffffff;
}

.item__stack {
  position: relative;
  height: 35px;
}

.label__stack {
  position: absolute;
  top: .235rem;
  right: -1rem;
  display: inline-block;
  padding: .235rem;
  color: #fff;
  background-color: rgba(0, 0, 0, .55);
  border: 1px solid rgba(0, 0, 0, .25);
  border-radius: 5px;
  opacity: 0;
  transition: opacity .3s;
  z-index: 1000;
}
.item__stack:hover .label__stack {
  opacity: 1;
}

.label__stack .decoration__stack {
  display: inline-block;
  width: 1rem;
  height: 1rem;
  background-color: inherit;
  border-radius: 50%;
  vertical-align: text-top;
  display: none;
}
</style>
