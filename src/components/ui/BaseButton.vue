<template>
	<button class="btn" :class="mode ?? 'btn-primary'">
		<slot></slot>	
	</button>
</template>

<script>
	export default {
		props: ['mode'],
	}
</script>

<style scoped>

</style>