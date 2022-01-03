<template>
  <button @click="load()" class="btn">reload</button>
</template>

<script>
export default {
  name: "Button",
  methods: {
    load() {
      this.$emit("btn-load");
    },
  },
  emits: ['btn-load'],
};
</script>
