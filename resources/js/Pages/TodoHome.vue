<template>
  <TodoLayout>
    <template #top>
      <TaskAdd />
      <TaskTab />
    </template>
    <Task
      v-for="todo in todos"
      :todo="todo"
      :key="todo.id"
      @toggle-task="toggleTask(todo.id)"
    />
  </TodoLayout>
</template>

<script>
import Task from "@/Components/Todo/Task.vue";
import TaskTab from "@/Components/Todo/TaskTab.vue";
import TaskAdd from "@/Components/Todo/TaskAdd.vue";
import TodoLayout from "@/Layouts/TodoLayout.vue";
export default {
  name: "TodoHome",
  components: {
    Task,
    TaskTab,
    TaskAdd,
    TodoLayout,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          task: "The Task 1",
          time: "Feb 10, 2022 at 10:00 AM",
          status: false,
        },
        {
          id: 2,
          task: "The Task 2",
          time: "Feb 10, 2022 at 10:00 AM",
          status: true,
        },
        {
          id: 3,
          task: "The Task 3",
          time: "Feb 10, 2022 at 10:00 AM",
          status: true,
        },
      ],
    };
  },
  methods: {
    toggleTask(todo_id) {
      this.todos.map((todo) => {
        todo.status = todo.id == todo_id ? !todo.status : todo.status;
        return todo;
      });
    },
  },
  computed: {},
};
</script>

<style>
</style>
