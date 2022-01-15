<template>
  <div id="headerview">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "我是標題",
    };
  },
  // 1.props
  props: {
    msg: {
      // 自定義屬性
      type: String,
      default: "Who am I?",
    },
  },
};
</script>

<style>
</style>