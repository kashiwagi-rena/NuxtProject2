<script setup lang="ts">
import productInformation from '../json/productInformation.json'

const positions = ref<{ top: number; left: number; duration: number; delay: number }[]>([])

onMounted(() => {
  const count = Object.keys(productInformation).length
  const result = []
  for (let i = 0; i < count; i++) {
    let top, left
    do {
      top  = Math.random() * 80 + 5
      left = Math.random() * 75 + 5
    } while (top > 35 && top < 65 && left > 25 && left < 75)
    result.push({
      top,
      left,
      duration: Math.random() * 4 + 4,
      delay:    Math.random() * 3,
    })
  }
  positions.value = result
})
</script>

<template>
	<main>
		<span class="meteor" />
		<h1>Project Hail Mary</h1>
		<div
			v-for="(value, key, index) in productInformation"
			:key="key"
			class="floatItem"
			:style="positions[index] ? {
				top:               positions[index].top      + '%',
				left:              positions[index].left     + '%',
				animationDuration: positions[index].duration + 's',
				animationDelay:    positions[index].delay    + 's',
			} : { display: 'none' }"
		>
			<DisplayButton :product-name="value.productName" :url="value.url" />
		</div>
	</main>
</template>

<style scoped lang="css">
main {
	min-height: 100vh;
	background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
	padding: 20px;
	position: relative;
	overflow: hidden;
}

main::before,
main::after {
	content: '';
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	pointer-events: none;
}

main::before {
	background-image:
		radial-gradient(1px 1px at 10% 20%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 30% 50%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 50% 10%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 70% 80%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 90% 35%, white 0%, transparent 100%),
		radial-gradient(1.5px 1.5px at 20% 75%, #aad4f5 0%, transparent 100%),
		radial-gradient(1.5px 1.5px at 55% 60%, #aad4f5 0%, transparent 100%),
		radial-gradient(1.5px 1.5px at 80% 15%, #aad4f5 0%, transparent 100%),
		radial-gradient(2px 2px at 40% 90%, white 0%, transparent 100%),
		radial-gradient(2px 2px at 65% 40%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 5% 55%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 85% 65%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 15% 90%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 45% 30%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 75% 5%, white 0%, transparent 100%),
		radial-gradient(1.5px 1.5px at 95% 50%, #ffd4aa 0%, transparent 100%),
		radial-gradient(1px 1px at 25% 15%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 60% 70%, white 0%, transparent 100%);
	animation: twinkle 4s ease-in-out infinite alternate;
}

main::after {
	background-image:
		radial-gradient(1px 1px at 8% 40%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 35% 25%, white 0%, transparent 100%),
		radial-gradient(1.5px 1.5px at 58% 85%, #aad4f5 0%, transparent 100%),
		radial-gradient(1px 1px at 78% 55%, white 0%, transparent 100%),
		radial-gradient(2px 2px at 92% 20%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 18% 60%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 48% 45%, white 0%, transparent 100%),
		radial-gradient(1.5px 1.5px at 68% 95%, #ffd4aa 0%, transparent 100%),
		radial-gradient(1px 1px at 3% 80%, white 0%, transparent 100%),
		radial-gradient(1px 1px at 88% 75%, white 0%, transparent 100%);
	animation: twinkle 6s ease-in-out infinite alternate-reverse;
}

@keyframes twinkle {
	0% { opacity: 0.4; }
	100% { opacity: 1; }
}

h1 {
	color: #fdd835;
	text-shadow: 0 0 10px rgba(253, 216, 53, 0.9), 0 0 24px rgba(253, 216, 53, 0.5), 0 0 48px rgba(255, 200, 0, 0.3);
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	z-index: 1;
	white-space: nowrap;
}

.floatItem {
	position: absolute;
	z-index: 1;
	animation: floating ease-in-out infinite alternate;
}

@keyframes floating {
	0%   { transform: translateY(0px) translateX(0px); }
	50%  { transform: translateY(-12px) translateX(5px); }
	100% { transform: translateY(-20px) translateX(-5px); }
}

/* 流れ星 */
.meteor {
	position: absolute;
	top: 0;
	left: 0;
	width: 2px;
	height: 80px;
	background: linear-gradient(to bottom, rgba(255,255,255,0), white);
	border-radius: 50%;
	transform: rotate(215deg);
	animation: meteor linear infinite;
	opacity: 0;
}

.meteor::after {
	content: '';
	position: absolute;
	top: 0;
	left: 50%;
	transform: translateX(-50%);
	width: 4px;
	height: 4px;
	border-radius: 50%;
	background: white;
	box-shadow: 0 0 6px 2px rgba(255,255,255,0.8);
}

.meteor {
	top: 50%;
	left: 50%;
	animation-duration: 12s;
}

@keyframes meteor {
	0%   { transform: rotate(215deg) translateX(0);   opacity: 0; }
	5%   { opacity: 1; }
	15%  { opacity: 1; }
	20%  { transform: rotate(215deg) translateX(500px); opacity: 0; }
	100% { transform: rotate(215deg) translateX(500px); opacity: 0; }
}

@media (max-width: 768px) {
	h1 {
		font-size: 1.2rem;
	}
}
</style>
