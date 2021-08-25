<template>
  <div v-for="task in tasks" :key="task.id">
    <Task
      @delete-task="onDelete(task.id)"
      @toggle-reminder="$emit(`toggle-reminder`, task.id)"
      :task="task"
    />
  </div>
</template>
<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: { tasks: Array },
  components: { Task },
  methods: {
    onDelete(id) {
      this.$emit("delete-task", id);
    },
  },
  emits: ["delete-task", `toggle-reminder`],
};
</script>
<style lang=""></style>
