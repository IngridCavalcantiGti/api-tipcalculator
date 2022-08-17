<template>
  <div>
    <button
      @click="() => $emit('onClick')"
      type="button"
      class="btn btn-dark rounded-5"
    >
      <i :class="`bi bi-chevron-${icon}`"></i>
    </button>
  </div>
</template>
<script>
export default {
  name: "Button",
  props: {
    icon: {
      type: String,
    },
  },
};
</script>
