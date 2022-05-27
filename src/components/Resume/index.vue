<template>
    <main>
        <p> {{ labelShow }}</p>
        <h1> {{ renderAmount }}</h1>
        <div class="graphic">
            <slot name="graphic"></slot>   
        </div>
        <div class="actio">
            <slot name="action"></slot>
        </div>
    </main>
</template>
<script>
const currencyFormatter = new Intl.NumberFormat("es-EC", {
  style: "currency",
  currency: "USD",
});
export default {
    props: {
        label: {
        type: String,
        },
        date: {
        type: String,
        default: null,
        },
        amount: {
        type: Number,
        default: null,
        },
        totalAmount: {
        type: Number,
        },
    },
    computed: {
        renderAmount() {
            return currencyFormatter.format(this.amount || this.totalAmount)
        },
        labelShow() {
            return this.date || this.label;
        }
    }
}
</script>
<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100vh;
}

h1,
p {
  margin: 0;
  text-align: center;
}

h1 {
  margin-top: 14px;
  color: var(--brand-green);
}
</style>