<script setup lang="ts">
interface Props {
  productName: string
  url: number
}

const props = defineProps<Props>();

const router = useRouter();

const onHandler = () => {
  router.push(`/${props.url}`)
}
</script>

<template>
  <button @click="onHandler" class="buttonWrap">
    <label>{{ props.productName }}</label>
  </button>
</template>

<style scoped lang="css">
.buttonWrap {
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 12px 16px;
}

label {
  color: #e8f4fd;
  font-size: 14px;
  font-weight: bold;
  cursor: pointer;
  white-space: nowrap;
  text-shadow:
    0 0 6px rgba(255, 255, 255, 1),
    0 0 12px rgba(170, 212, 245, 0.9),
    0 0 24px rgba(170, 212, 245, 0.6),
    0 0 48px rgba(100, 160, 255, 0.4);
  animation: flicker 4s ease-in-out infinite alternate;
}

@keyframes flicker {
  0%   { text-shadow: 0 0 6px rgba(255,255,255,1), 0 0 12px rgba(170,212,245,0.9), 0 0 24px rgba(170,212,245,0.6), 0 0 48px rgba(100,160,255,0.4); }
  100% { text-shadow: 0 0 8px rgba(255,255,255,1), 0 0 18px rgba(170,212,245,1),   0 0 36px rgba(170,212,245,0.8), 0 0 64px rgba(100,160,255,0.6); }
}

@media (max-width: 768px) {
  label {
    font-size: 12px;
  }
}
</style>
