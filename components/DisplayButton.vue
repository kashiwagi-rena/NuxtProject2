<script setup lang="ts">
interface Props {
  productName: string
  unitPrice: number
}

const props = defineProps<Props>();
</script>

<template>
  <button class="buttonWrap">
    <label>{{ props.productName }}</label>
    <div>{{ props.unitPrice }}円</div>
  </button>
</template>

<style scoped lang="css">
.buttonWrap {
  width: 100%;
  min-height: 60px;
  background-color: antiquewhite;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
