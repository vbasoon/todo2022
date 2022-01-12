<template>
  <div class="wrapper">
    <Header />

    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>{{ headling }}</h1>

    <div class="todo-form">
      <h2>Add Todo</h2>
      <form @submit.prevent="addTask" action="">
        <input v-model="task" type="text" name="" id="" />
        <input type="submit" value="Send" />
      </form>
    </div>

    <div class="todo-list">
      <h2>Todo List</h2>
      <ul class="todo-list__body todo">
        <li v-for="(task, idx) in todos" :key="idx" class="todo__item">
          <div>
            <input
              v-model="task.isComplete"
              :value="true"
              class="todo__item-checkbox"
              type="checkbox"
            />
            <span
              class="todo__item-info"
              :class="{ 'line-through': task.isComplete }"
              >{{ task.nameTask }}</span
            >
          </div>
          <div><button @click="deleteTask(idx)">Delete</button></div>
        </li>
      </ul>
    </div>

    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
export default {
  data() {
    return {
      headling: "Todo2022",
      todos: [],
      task: "",
    };
  },
  components: {
    Header,
    Footer,
  },
  methods: {
    addTask() {
      this.todos.push({
        nameTask: this.task,
        isComplete: false,
      });
      this.task = "";
    },
    deleteTask(idx) {
      this.todos.splice(idx, 1);
    },
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

.line-through {
  text-decoration: line-through;
}

.todo-form,
.todo-list {
  margin-left: 350px;
  max-width: 720px;
  padding: 20px;
  background: #e5e5e5;
  border: 5px solid #2c3e50;
  border-radius: 30px;
}

.todo-form {
  padding: 20px;
  margin-bottom: 20px;
}

.todo-list {
  height: 360px;
  padding: 20px;
  overflow: hidden;
  margin-bottom: 20px;

  &__body {
    overflow-y: scroll;
    border: 2px solid red;
    height: 270px;

    .todo {
      &__item {
        display: flex;
        padding: 10px;
        border: 1px solid #2c3e50;
        justify-content: space-between;
        margin-bottom: 16px;
        &-checkbox {
          margin-right: 16px;
        }
      }
    }
  }
}
</style>
