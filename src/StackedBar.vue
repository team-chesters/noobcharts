<template>
  <div class="wrap__stack">
    <div
    class="item__stack"
    v-for="(item, index) in data"
    :key="index"
    :style="bgColor(item, index)+'flex-basis:' + item.percent +'%;'"
    data-color="">
      <div class="percent__stack">
        <span class="text__stack">
          <strong>{{item.percent}}%</strong>
        </span>
      </div>
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

<style src="./StackedBar.css" scoped />

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
