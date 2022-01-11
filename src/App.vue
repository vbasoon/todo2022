<template>
  <Header />

  <img alt="Vue logo" src="./assets/logo.png" />
  <h1>{{ title }}</h1>
  <div class="wrapper">
    <div class="todo-form">
      <h2>Add Todo</h2>
      <form action="">
        <input type="text" name="" id="" />
        <input type="submit" value="Send" />
      </form>
    </div>
    <hr />
    <div class="todo-list">
      <h2>Todo List</h2>
      <ul class="todo-list__body todo">
        <li class="todo__item">Todo1</li>
        <li class="todo__item">Todo2</li>
        <li class="todo__item">Todo3</li>
        <li class="todo__item">Todo4</li>
      </ul>
    </div>
  </div>
  <Footer />
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
export default {
  data() {
    return {
      title: "Todo2022",
    };
  },
  components: {
    Header,
    Footer,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: rgb(34, 70, 195);
  background: linear-gradient(
    144deg,
    rgba(34, 70, 195, 1) 0%,
    rgba(253, 240, 45, 1) 100%
  );
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  width: 100%;
  height: 100vh;
}

.wrapper {
  max-width: 1440px;
  width: 100%;
  margin: 0 auto;
  height: 100vh;
  overflow: hidden;
}

h1 {
  margin-bottom: 20px;
}

h2 {
  margin-bottom: 1rem;
}

li {
  list-style-type: none;
}

a {
  text-decoration: none;
  color: inherit;
}

.todo-form {
  padding: 20px;
  margin-bottom: 20px;
}

.todo-list {
  padding: 20px;
  .todo {
    &__item {
      margin-bottom: 16px;
    }
  }
}
</style>
