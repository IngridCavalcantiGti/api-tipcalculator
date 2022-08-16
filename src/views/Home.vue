<template>
  <div>
    <div class="d-flex flex-wrap justify-content-center mt-5">
      <h1>Le/Tip</h1>
    </div>
    <div class="ms-5 d-flex flex-wrap justify-content-center">
      <div>
        <Switch></Switch>
        <Input label="Valor" :icon="icon" />
        <Range label="Gorjeta" numberMin="10" numberMax="20" class="mt-3" />
        <Range label="Pessoas" numberMin="2" numberMax="6" />
      </div>
    </div>
  </div>
</template>

<script>
import Input from "../components/Input.vue";
import Range from "../components/Range.vue";
import Switch from "../components/Switch.vue";

export default {
  components: { Input, Range, Switch },
  setup() {},
};
</script>

