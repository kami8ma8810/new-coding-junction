<template>
  <div class="post" v-html="body"></div>
</template>

<script>
export default {
  props: {
    body: {
      type: String,
      required: true,
      default: '',
    },
  },
};
</script>
