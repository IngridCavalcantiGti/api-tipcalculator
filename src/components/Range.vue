<template>
  <div>
    <label for="customRange1">{{ label }}</label>
    <span class="ms-1">
      <slot name="value">
        {{ modelValue }}
      </slot>
    </span>
    <div class="d-flex">
      <span class="me-3">{{ numberMin }}</span>
      <input
        type="range"
        id="customRange1"
        :value="modelValue"
        @input="updateInput($event.target.value)"
        :min="numberMin"
        :max="numberMax"
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
    modelValue: {
      type: Number,
    },
    numberMin: {
      type: Number,
    },
    numberMax: {
      type: Number,
    },
  },

  setup(props, { emit }) {
    const updateInput = (value) => {
      emit("update:modelValue", Number(value));
    };
    return {
      updateInput,
    };
  },
};
</script>
