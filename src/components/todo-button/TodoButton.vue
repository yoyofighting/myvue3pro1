<template>
<div class="button-container" mt-3>
  <div class="btn-group" role="group" aria-label="Basic example">
    <button type="button" class="btn" :class="active === 0? 'btn-primary' : 'btn-secondary'" @click="updateIndex(0)">全部</button>
    <button type="button" class="btn" :class="active === 1? 'btn-primary' : 'btn-secondary'" @click="updateIndex(1)">已学习</button>
    <button type="button" class="btn" :class="active === 2? 'btn-primary' : 'btn-secondary'" @click="updateIndex(2)">未学习</button>
  </div>
</div>
</template>

<script>
export default {
  name: 'TodoButton',
  // 当时写成['update: active'],多了个空格就不出效果？
  emits: ['update:active'],
  props: {
    active: {
      type: Number,
      required: true,
      default: 0
    }
  },
  methods: {
    updateIndex(index) {
      if(index === this.active) return
      this.$emit('update:active', index)

    }
  }
}
</script>
<style lang="less" scoped>
.button-container {
  width: 400px;
  text-align: center;
}
</style>
