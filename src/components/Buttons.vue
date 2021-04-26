<template>
  <button @click="onClick()" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Buttons",
  props: ["text", "color"],
  methods: {
    onClick() {
        console.log("Button invoked..!")
        this.$emit('btn-click')
    },
  },
};
</script>

<style scoped>
</style>