<template>
  <div class="d-flex align-items-center">
    <span class="form-check-label me-2">EUR</span>
    <label class="switch">
      <input type="checkbox" v-model="value" />
      <span class="slider"></span>
    </label>
    <span class="form-check-label ms-2">USD</span>
  </div>
</template>
<script>
import { computed } from "vue";
export default {
  props: {
    modelValue: {
      type: Boolean,
    },
  },
  setup(props, { emit }) {
    const value = computed({
      get() {
        return props.modelValue;
      },
      set(inputValue) {
        emit("update:modelValue", inputValue);
      },
    });

    return { value };
  },
};
</script>
<style scoped>
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input + .slider {
  background-color: #2196f3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}
</style>