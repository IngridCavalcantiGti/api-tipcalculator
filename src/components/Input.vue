<template>
  <label class="d-flex align-items-center">
    <span class="label me-2"> {{ label }}</span>
    <i :class="`bi bi-currency-${icon}`"></i>
    <div>
      <input
        type="text"
        @input="updateInput($event.target.value)"
        :value="value"
      />
    </div>
  </label>
</template>

<script>
export default {
  name: "Input",
  props: {
    label: {
      type: String,
    },
    value: {
      type: String,
    },
    icon: {
      type: String,
      default: "dollar",
    },
  },
  setup(props, { emit }) {
    const updateInput = (value) => {
      emit("onInput", value);
    };
    return {
      updateInput,
    };
  },
};
</script>
<style scoped>
.label {
  font-size: 1rem;
}
input {
  width: 7rem;
}
</style>