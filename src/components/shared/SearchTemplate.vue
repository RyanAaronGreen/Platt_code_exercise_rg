<template>
  <div>
    <span>{{ item[0] }}</span>
  </div>
</template>

<script>
export default {
  props: {
    item: { required: true },
  },
};
</script>
