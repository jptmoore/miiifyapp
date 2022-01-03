<template>
  <div>
    <h1>{{ title }}</h1>
    <Button
      @btn-load="$emit('button-load')"
      @btn-save="$emit('button-save')"
    />
  </div>
</template>

<script>
import Button from "./Button";

export default {
  name: "Footer",
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
div {
  margin-bottom: 20px;
}
</style>
