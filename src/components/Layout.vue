<template>
    <div class="header">
        <slot name="header"></slot>
    </div>
    <div class="resume">
      <slot name="resume"></slot>
    </div>
    <div class="movements">
      <div class="head" @click="showMovements = !showMovements">
        <div class="grip"></div>
      </div>
      <div class="body" v-show="showMovements">
        <slot name="movements"></slot>
      </div>
    </div>
</template>
<script setup>
  import { ref } from 'vue'
  const showMovements = ref(false)
</script>
<style scoped>
.header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100vw;
}
img,
span {
  width: 48px;
}
h1 {
  font-size: 1.4rem;
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
.movements {
  max-height: 100%;
  padding: 0 8px;
  margin-bottom: 14px;
}

.title {
  margin: 8px 16px 24px 16px;
  color: var(--brand-blue);
}

.content {
  max-height: 68vh;
  display: flex;
  flex-direction: column;
  gap: 8px;
  overflow-y: scroll;
}
</style>