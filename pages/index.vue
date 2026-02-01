<script setup lang="ts">
import productInformation from '../json/productInformation.json'
</script>

<template>
	<main>
		<form class="DisplayButtonWrap">
			<div v-for="(value, key) in productInformation" :key="key">
				<DisplayButton :product-name="value.productName" :unit-price="value.unitPrice" />
			</div>
		</form>
	</main>
</template>

<style scoped lang="css">
.DisplayButtonWrap {
	display: flex;
	flex-wrap: wrap;
	gap: 10px;
}

.DisplayButtonWrap > div {
	flex: 0 0 calc(33.333% - 7px);
}
</style>
