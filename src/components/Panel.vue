<template>
  <div class="flex-column d-sm-flex gap-3">
    <div>
      <h2>Conta</h2>
      <i :class="`bi bi-currency-${icon}`" />
      {{ account }}
    </div>
    <div>
      <h2>Gorjeta</h2>
      <i :class="`bi bi-currency-${icon}`" />
      {{ tip }}
    </div>
    <div>
      <h2>Total</h2>
      <i :class="`bi bi-currency-${icon}`" />
      {{ total }}
    </div>
    <div>
      <h2>por Pessoa</h2>
      <i :class="`bi bi-currency-${icon}`" />
      {{ perPerson }}
    </div>
    <div>
      <h2>em R$</h2>
      <span>
        R$
        {{ coin }}
      </span>
    </div>
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
      type: String,
    },
    total: {
      type: String,
    },
    perPerson: {
      type: String,
    },
    coin: {
      type: String,
    },
  },
};
</script>
