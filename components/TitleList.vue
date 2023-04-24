<template>
  <div
    style="
      margin-top: 50px;
      border-bottom: 2px solid #86929e;
    "
  >
    <h1 style="margin-bottom: 0.5rem; color: #fff">{{ content }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    content: String,
  },
  data() {
    return {};
  },
};
</script>

<style></style>
