<template>
  <div class="wrap__stack">
    <div
     class="item__stack"
     v-for="(item, index) in data"
     :style="bgColor(item,index) + ' flex-basis:' + item.value +'%;'"
     :key="index">
      <span
      class="label__stack"
      v-if="item.text && item.title">
        <strong>
          {{item.title}}
        </strong>
        &nbsp;&colon;&nbsp;
        <span>
          {{item.text}}
        </span>
      </span>
      <span
      class="label__stack"
      v-else-if="!item.text && item.title">
        <strong>
          {{item.title}}
        </strong>
      </span>
      <span
      class="label__stack"
      v-else>
        <span>
          {{item.value}}
        </span>
      </span>
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
        // eslint-disable-next-line
      } else {
        const randomChoice = this.colors[Math.floor(Math.random() * this.colors.length)];
        return `background-color:${randomChoice};`;
      }
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
  height: 35px;
  /* line-height: 35px; */
}
.label__stack {
  display: inline-block;
  padding: .25rem .75rem;
  color: #ffffff;
  background-color: rgba(0, 0, 0, .55);
}
</style>
