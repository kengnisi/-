<template>
  <a :title="title" style="margin: 10px">
    <el-button v-bind="$attrs" v-on="$listeners"></el-button>
  </a>
</template>

<script>
export default {
  name: 'HintButton',
  props: ['title'],
  data() {
    return {

    };
  },
};
</script>

<style lang="less" scoped>

</style>
