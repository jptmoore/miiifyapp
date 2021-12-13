<template>
  <controls>
    <h1>{{ title }}</h1>
    <Button
      @btn-load="$emit('button-load')"
      @btn-save="$emit('button-save')"
    />
  </controls>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  props: {
    title: String,
  },
  components: {
    Button,
  },
  computed: {},
};
</script>

<style scoped>
controls {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 20px;
}
</style>
