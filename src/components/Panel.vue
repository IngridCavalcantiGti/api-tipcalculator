<template>
  <div class="flex-column d-sm-flex">
    <span class="mb-3">
      Conta
      <i :class="`bi bi-currency-${icon}`" class="d-block"> {{ account }}</i>
    </span>
    <span class="mb-3">
      Gorjeta
      <i :class="`bi bi-currency-${icon}`" class="d-block"> {{ tip }}</i>
    </span>
    <span class="mb-3">
      Total
      <i :class="`bi bi-currency-${icon}`" class="d-block"> {{ total }}</i>
    </span>
    <span class="mb-3">
      por Pessoa
      <i :class="`bi bi-currency-${icon}`" class="d-block">{{ perPerson }}</i>
    </span>
    <span class="mb-3"> em R<i :class="`bi bi-currency-${icon}`"></i> </span>
    <span class="mb-3"
      >R<i :class="`bi bi-currency-${icon}`">{{ coin }}</i>
    </span>
  </div>
</template>
<script>
export default {
  name: "Panel",
  props: {
    icon: {
      type: String,
      default: "dollar",
    },
    account: {
      type: Number,
    },
    tip: {
      type: Number,
    },
    total: {
      type: Number,
    },
    perPerson: {
      type: Number,
    },
    coin: {
      type: Number,
    },
  },
};
</script>
