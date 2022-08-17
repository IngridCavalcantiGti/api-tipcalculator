<template>
  <div>
    <div class="d-flex flex-wrap justify-content-center mt-5">
      <h1 class="mt-5">Le/Tip</h1>
    </div>
    <div class="ms-5 d-flex flex-wrap justify-content-center mt-5 fs-5 gap-5">
      <div
        class="tip-form d-sm-flex flex-column gap-3"
        :class="showPanel ? 'd-none' : 'd-flex'"
      >
        <Switch class="mt-3" v-model="currency"></Switch>
        <Input
          class="mt-5"
          label="Valor"
          icon="icon"
          v-model="account"
          @update:modelValue="calculate"
        />
        <Range
          label="Gorjetas"
          :numberMin="10"
          :numberMax="20"
          class="mt-5"
          v-model="tip"
          @update:modelValue="calculate"
        >
          <template #value>{{ tip }}% </template>
        </Range>
        <Range
          label="Pessoas"
          :numberMin="2"
          :numberMax="16"
          class="mt-5"
          v-model="people"
          @update:modelValue="calculate"
        />
      </div>
      <Panel
        :class="showPanel ? 'd-flex' : 'd-none'"
        :account="account"
        :tip="calculatedTip"
        :total="total"
        :perPerson="perPerson"
        :coin="coin"
      ></Panel>
    </div>
    <div class="d-flex justify-content-end">
      <Button
        :icon="showPanel ? 'left' : 'right'"
        @onClick="togglePanel"
        class="d-block d-sm-none"
      ></Button>
    </div>
  </div>
</template>

<script>
import Input from "../components/Input.vue";
import Range from "../components/Range.vue";
import Switch from "../components/Switch.vue";
import Panel from "../components/Panel.vue";
import Button from "../components/Button.vue";
import { ref } from "vue";

export default {
  components: { Input, Range, Switch, Panel, Button },
  setup() {
    const showPanel = ref(false);

    const togglePanel = () => {
      showPanel.value = !showPanel.value;
    };

    const currency = ref("USD");
    const account = ref(0);
    const tip = ref(10);
    const people = ref(2);
    const calculatedTip = ref();
    const total = ref();
    const perPerson = ref();
    const coin = ref();

    const calculate = () => {
      const newTip = account.value * (tip.value / 100);
      calculatedTip.value = newTip.toFixed(2);
      total.value = (account.value + newTip).toFixed(2);
      perPerson.value = (total.value / people.value).toFixed(2);
    };

    return {
      togglePanel,
      showPanel,
      calculate,
      currency,
      account,
      tip,
      people,
      calculatedTip,
      total,
      perPerson,
      coin,
    };
  },
};
</script>


