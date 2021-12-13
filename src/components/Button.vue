<template>
  <button @click="load()" class="btn">load</button>
  <button @click="save()" class="btn">save</button>
</template>

<script>
export default {
  name: "Button",
  methods: {
    load() {
      this.$emit("btn-load");
    },
    save() {
      this.$emit("btn-save");
    },
  },
  emits: ['btn-load', 'btn-save'],
};
</script>
