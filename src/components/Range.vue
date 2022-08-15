<template>
  <div>
    <label for="customRange1">{{ label }}</label>
    <span>{{ numberRange }}</span>
    <div class="d-flex">
      <span class="me-3">{{ numberMin }}</span>
      <input
        type="range"
        id="customRange1"
        :value="value"
        @input="updateInput($event.target.value)"
      />
      <span class="ms-3">{{ numberMax }}</span>
    </div>
  </div>
</template>


<script>
export default {
  name: "Range",
  props: {
    label: {
      type: String,
    },
    value: {
      type: String,
    },
    numberRange: {
      type: String,
    },
    numberMin: {
      type: String,
    },
    numberMax: {
      type: String,
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
