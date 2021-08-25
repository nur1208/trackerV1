<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      @click="$emit(`toggle-add-task`)"
      :text="isAddOpen ? `Close` : `Show Add Task`"
      :color="isAddOpen ? `red` : `green`"
    />
  </header>
</template>
<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  //   props: ["title"],
  props: { title: String, isAddOpen: Boolean },
  //   props: { title: { type: String, default: "hello John" } },
  components: {
    Button,
  },
};
</script>

<style scoped>
/* scoped mean this style only for this compo */

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
