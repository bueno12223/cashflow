<template>
    <div class="movement">
        <div class="content">
            <h4>{{ title }}</h4>
            <p> {{ description }}</p>
        </div>
        <div class="action">
            <img src="../../assets/trash-icon.svg" alt="borrar" @click="remove">
            <p>{{ renderAmount }}</p>
        </div>
    </div>
</template>

<script setup>
import { toRefs, defineProps, computed } from 'vue';
const props = defineProps({
    id: {
        type: Number,
        default: 0,
    },
    title: {
        type: String,
    },
    description: {
        type: String,
    },
    amount: {
        type: String,
    },
});
const currencyFormatter = new Intl.NumberFormat("es-EC", {
  style: "currency",
  currency: "USD",
});
const { title, description, id, amount } = toRefs(props);
const renderAmount = computed(() => currencyFormatter.format(amount.value));
const remove = () => {
    console.log(id.value)
}
</script>
<style scoped>
.movement {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 16px;
  background-color: #e6f9ff;
  border-radius: 8px;
  box-sizing: border-box;
}
.movement .content {
  width: 100%;
}
.movement .action {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  flex-direction: column;
}
h4,
p {
  margin: 0;
  padding: 0;
}
h4 {
  margin-bottom: 8px;
}
.movement .action img {
  margin-bottom: 16px;
}
.red {
    color: red;
}
.green {
    color: green;
}
</style>