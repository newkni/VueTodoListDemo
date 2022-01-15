<template>
  <div id="app">
    <HeaderView v-bind:msg="title"></HeaderView>
    <img alt="Vue logo" src="./assets/logo.png" />
    <ListView v-on:myMsg="getData"></ListView>
  </div>
</template>

<script>
import ListView from "./components/List.vue";
import HeaderView from "./components/Header.vue";
// app.vue 是父組件，ListView是子組件
// 父 to 子 = 透過props屬性
// 子 to 父 = 自定義事件，透過this.$emit('事件名稱',欲傳遞資訊)

export default {
  name: "app",
  components: {
    ListView,
    HeaderView,
  },
  data() {
    return {
      title: "Vue入門",
    };
  },
  methods: {
    getData(msg) {
      console.log("app.vue : " + msg);
      this.title = msg;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
