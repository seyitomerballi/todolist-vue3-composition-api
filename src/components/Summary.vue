<template>
  <div>
    <div>
      <small class="text-green-300">{{ completed }} adet tamamlanmış göreviniz bulunuyor.</small>
    </div>

    <div>
      <small class="text-red-300">{{ uncompleted }} adet tamamlanmamış göreviniz bulunuyor.</small>
    </div>
  </div>
</template>
<script>
import { computed } from "vue";
export default {
  props: {
    todoList: Array,
  },
  setup(props) {
    const completed = computed(() => props.todoList.filter((i) => i.completed).length);
    const uncompleted = computed(() => props.todoList.filter((i) => !i.completed).length)

    return { completed, uncompleted}
  },
};
</script>