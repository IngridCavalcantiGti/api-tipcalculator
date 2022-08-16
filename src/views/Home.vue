<template>
  <div>
    <div class="d-flex flex-wrap justify-content-center mt-5">
      <h1 class="mt-5">Le/Tip</h1>
    </div>
    <div class="ms-5 d-flex flex-wrap justify-content-center mt-5 fs-5">
      <div class="me-5">
        <Switch class="mb-3 mt-3"></Switch>
        <Input class="mb-3 mt-5" label="Valor" :icon="icon" />
        <Range
          label="Gorjeta"
          numberMin="10"
          numberMax="20"
          class="mt-5 mb-3"
        />
        <Range label="Pessoas" numberMin="2" numberMax="16" class="mb-3 mt-5" />
      </div>
      <div class="ms-5">
        <Panel></Panel>
      </div>
    </div>
  </div>
</template>

<script>
import Input from "../components/Input.vue";
import Range from "../components/Range.vue";
import Switch from "../components/Switch.vue";
import Panel from "../components/Panel.vue";

export default {
  components: { Input, Range, Switch, Panel },
  setup() {},
};
</script>

