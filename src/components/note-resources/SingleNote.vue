<template>
	<base-card>
		<header>
			<h3>{{ title }}</h3>
			<span>
				<base-button mode="btn-flat">Delete</base-button>
			</span>
		</header>
		<p>
			{{ description }}
		</p>
	</base-card>
</template>

<script>

	export default {
		props: ['title', 'description'],
	}
</script>

<style scoped>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 10px;
	}

</style>