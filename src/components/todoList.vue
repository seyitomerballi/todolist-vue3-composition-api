<template>
  <section class="mt-4">
    <TodoListItem @delete-event="$emit('delete-event',$event)" v-for="todoItem in todoList" :key="todoItem.id" :todo="todoItem" />
    <Summary :todoList="todoList" class="mt-5" />
    <small class="text-md font-bold">Toplam {{todoLength}} adet göreviniz vardır.</small>
  </section>
</template>
<script>
import TodoListItem from "./todoListItem.vue";
import Summary from "./Summary.vue";
import { computed } from "vue";
export default {
  components: { TodoListItem, Summary },
  props: {
    todoList: Array,
  },
  setup(props) {
    const todoLength = computed(() => props.todoList.length);
    return {
      todoLength,
    };
  },
};
</script>