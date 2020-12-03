<template>
	<the-header title="My Notes"></the-header>
	<div class="image">
		<img alt="Vue logo" src="./assets/logo.png">
	</div>
	<the-resource></the-resource>
</template>

<script>
	import TheHeader from './components/layouts/TheHeader.vue';
	import TheResource from './components/note-resources/TheResource.vue';

	export default {
		name: 'App',
		components: {
			TheHeader,
			TheResource,
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
	
	:root {
		--primary: #007791;
	}
	* {
		box-sizing: border-box;
	}

	html {
		font-family: 'Roboto', sans-serif;
	}

	body {
		margin: 0;
	}

	#app {
		color: #2c3e50;
	}
	.image {
		text-align: center;
	}
</style>
