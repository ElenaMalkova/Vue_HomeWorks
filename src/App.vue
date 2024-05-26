<template>
  <div id="app">
    <a href="index.html">Вернуться</a>
    <h2>Разворот текста</h2>
    <button class="vue-btn" @click="reverseMessage">{{ message }}</button>
    <div class="top-gap_96">
      <h2>Добавление строки списка</h2>
      <button class="vue-btn" @click="addNewItem">Добавить</button>
      <ul>
        <li v-for="(item, index) in list" :key="index">
          {{ item }}
          <button class="vue-btn" @click="removeItem(index)">Удалить</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Перевернуть',
      reversedMessage: '',

      // Массив для списка
      list: []
    };
  },
  methods: {
    // Метод разворота текста
    reverseMessage() {
      this.message = this.message.split('').reverse().join('');
    },

    // Добавление строки по клику
    addNewItem() {
      this.list.push("Новый элемент списка");
    },

    // Удаление по клику на строке
    removeItem(index) {
      this.list.splice(index, 1);
    }
  },
};



</script>


<style scoped>
  .vue-btn {
    padding: 16px;
  }
  .top-gap_96 {
    margin-top: 96px;
    padding-bottom: 96px;
  }
</style>