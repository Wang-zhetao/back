<template>
  <div>
    <ul class="types">
      <li :class="type === '-' && 'selected'" 
      @click="selectedType('-')">支出</li>
      <li :class="type === '+' && 'selected'"
      @click="selectedType('+')">收入</li>
    </ul>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import {Component} from 'vue-property-decorator'
  
  @Component({
    props: {
      propMessage: String
    }
  })
  export default class Types extends Vue {
    type = '-'; // '-'表示支出，'+'表示收入
    helloMsg = 'Hello, ' + this.propMessage;
    propMessage: string|undefined;
    selectType(type: string) { // type 只能是 '-' 和 '+' 中的一个
      if (type !== '-' && type !== '+') {
        throw new Error('type is unknown');
      }
      this.type = type;
    }
    created() {}
    mounted() {}
  }
  
</script>

<style lang="scss" scoped>
  .types {
    background: #c4c4c4;
    display: flex;
    text-align: center;
    font-size: 24px;
    > li {
      width: 50%;
      height: 64px;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      &.selected::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 4px;
        background: #333;
      }
    }
  }
</style>
