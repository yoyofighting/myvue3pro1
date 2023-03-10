<template>
<form class="form-inline" @submit.prevent="onFormSubmit">
  <div class="input-group mb-2 mr-sm-2">
    <div class="input-group-prepend">
      <div class="input-group-text">*</div>
    </div>
    <input type="text" class="form-control" id="inlineFormInputGroupUsername2" placeholder="请填写新的学习内容" style="width: 350px;" v-model.trim="taskname">
  </div>

  <button type="submit" class="btn btn-primary mb-2">提交</button>
</form>
</template>

<script>
export default {
  name: 'TodoInput',
  emits: ['add'],
  data() {
    return {
      // 新任务的名称
      taskname: ''
    }
  },
  methods: {
    onFormSubmit() {
      if(!this.taskname) return alert('内容不能为空！')
      this.$emit('add', this.taskname);
      this.taskname = '';

    }
  }
}
</script>
<style lang="less" scoped>
</style>
