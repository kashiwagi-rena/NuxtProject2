<script setup lang="ts">
interface Props {
  title: string;
  body: string;
}

const props = defineProps<Props>();
</script>

<template>
  <div>
    <label>{{ props.title }}</label>
    <div>{{ props.body }}</div>
  </div>
</template>

<style scoped lang="css">
</style>
