<template>
  <section class="w-full">
    <input
      @keydown.enter="newItem"
      class="
        w-full
        p-2
        bg-gray-700
        border-[1px] border-gray-400
        rounded-md
        outline-none
      "
      placeholder="Nedir?"
      type="text"
    />
  </section>
</template>
<script>
export default {
  props: {
    AddTodo: Function,
  },
  setup(props) {
    const newItem = (event) => {
      props.AddTodo(event.target.value);
      event.target.value = "";
    };

    return {
        newItem
    }
  },
};
</script>