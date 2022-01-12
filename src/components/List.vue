<template>
  <div class="view">
    <h1 class="title">{{ title }}</h1>

    <ul>
      <li v-for='item in items' :class="{finish:item.isFinished}" :key="item.text">
        {{ item.text }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  // data:{}
  // data: function(){ return {}}
  data() {
    return {
      title: "TodoList", // 標題
      items: [
        // 代辦事項
        {
          text: "練習Vue",
          isFinished: false,
        },
        {
          text: "練習 Docker",
          isFinished: true,
        },
      ],
    };
  },
};
</script>

<style>
.view {
  width: 400px;
  border: 1px solid gray;
  margin: 20px auto;
}
.view .title{
    border-bottom: 1px solid gray;
}
.view ul li{
    margin: 10px 0;
    list-style: none;
}
.view .finish{
    color: gray;
    text-decoration: line-through;
}
</style>