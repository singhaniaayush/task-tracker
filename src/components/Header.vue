<template>
  <header>
    <h1>{{ title }}</h1>
    <div>
      <Button
        v-show="homePage"
        @btn-click="$emit('toggle-add-task')"
        :text="showAddTask ? 'Close' : 'Add Task'"
        :color="showAddTask ? 'red' : 'green'"
      />
    </div>
  </header>
</template>

<script>
import Button from "./Buttons";

export default {
  name: "Header",
  // multiple ways to define prop
  //   props: ["title"],
  props: {
    // setting default values to a prop
    title: {
      type: String,
      default: "Welcome to Task Tracker",
    },
    showAddTask: Boolean,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
  components: { Button },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>