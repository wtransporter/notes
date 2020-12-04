<template>
	<div @click="$emit('close')"></div>
	<dialog open>
		<header>
			<h3>{{ title }}</h3>
		</header>
		<section>
			<slot></slot>
		</section>
		<menu>
			<slot name="actions"></slot>
		</menu>
	</dialog>
</template>

<script>
	export default {
		props: ['title'],
	}
</script>

<style scoped>
	dialog {
		position: fixed;
		top: 20vh;
		left: 5%;
		width: 400px;
		padding: 0;
		border: none;
		border-radius: 5px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
		z-index: 100;
		overflow: hidden;
	}

	header {
		background-color: var(--primary);
		padding: 8px;
		width: 100%;
	}
	
	header h3 {
		color: white;
		margin: 0;
	}

	section {
		padding: 0 8px;
	}

	menu {
		display: flex;
		justify-content: flex-end;
		padding: 5px;
		margin: 0;
	}

	div {
		position: fixed;
		height: 100vh;
		width: 100%;
		background-color: rgba(0, 0, 0, 0.26);
		top: 0;
		left: 0;
		z-index: 10;
	}
</style>