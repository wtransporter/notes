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
	.btn {
		font-family: inherit;
		border: 1px solid rgb(255, 255, 255);
		color: white;
		cursor: pointer;
		outline: 0;
		padding: 5px 15px;
	}
	.btn-primary {
		background-color: var(--primary);
		color: white;
	}
	.btn-primary:hover, .btn-primary:active {
		
		background-color: #4aa5b9;
		border: 1px solid #4aa5b9;
	}

	.btn-primary:focus {
		border: 1px solid var(--primary);
	}
	.btn-flat {
		background-color: transparent;
		color: var(--primary);
		font-weight: bold;
	}
	.btn-flat:hover {
		border: 1px solid var(--primary);
	}

	.btn-flat:focus {
		border: 1px solid var(--primary);
	}
</style>