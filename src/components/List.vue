<template>
  <div class="view">
    <h1 class="title">{{ title }}</h1>

    <input v-model="newTodoList" @keyup.enter="addTodoList" />

    <ul>
      <li
        v-for="item in items"
        :class="{ finish: item.isFinished }"
        :key="item.text"
        @click="toggleFinish(item)"
      >
        {{ item.text }}
      </li>
    </ul>
  </div>
</template>

<script>
// 相當於 new Vue()
export default {
  name: "List",
  // data:{}
  // data: function(){ return {}}
  data() {
    return {
      title: 'TodoList', // 標題
      items: [
        // 代辦事項
        // {
        //   text: '練習Vue',
        //   isFinished: false,
        // },
        // {
        //   text: '練習 Docker',
        //   isFinished: true,
        // },
      ],
      newTodoList: '',
    };
  },
  methods: {
    toggleFinish: function (item) {
      item.isFinished = !item.isFinished;
    },
    addTodoList: function () {
      this.items.push({ text: this.newTodoList, isFinished: false });
      // 傳遞資訊給父組件
      // 觸發myMsg事件，並且傳遞參數(this.addTodoList)
      this.$emit('myMsg', this.newTodoList);
      this.newTodoList = '';

    },
  },
};
</script>

<style>
.view {
  width: 400px;
  border: 1px solid gray;
  margin: 20px auto;
}
.view .title {
  border-bottom: 1px solid gray;
}
.view ul li {
  margin: 10px 0;
  list-style: none;
}
.view .finish {
  color: gray;
  text-decoration: line-through;
}
</style>