<template>
	<the-header title="My Notes"></the-header>
	<img alt="Vue logo" src="./assets/logo.png">
	<section>
		<div class="content">
			<base-button>All Notes</base-button>
			<base-button mode="btn-flat">Add Note</base-button>
		</div>
	</section>
	<section class="grid">
		<div v-for="note in notes" :key="note.id">
			<header>
				<h3>{{ note.title }}</h3>
				<span>
					<base-button mode="btn-flat">Delete</base-button>
				</span>
			</header>
			<p>
				{{ note.description }}
			</p>
		</div>
	</section>
</template>

<script>
	import TheHeader from './components/layouts/TheHeader.vue';

	export default {
		name: 'App',
		components: {
			TheHeader
		},
		data() {
			return {
				notes: [
					{
						id: 1,
						title: 'Note 1 title',
						description: 'Note 1 test description.'
					},
					{
						id: 2,
						title: 'Note 2 title',
						description: 'Note 2 test description.'
					},
					{
						id: 3,
						title: 'Note 3 title',
						description: 'Note 3 test description.'
					},
					{
						id: 4,
						title: 'Note 4 title',
						description: 'Note 4 test description.'
					},
					{
						id: 5,
						title: 'Note 5 title',
						description: 'Note 5 test description.'
					},
					{
						id: 6,
						title: 'Note 6 title',
						description: 'Note 6 test description.'
					}
				],
			};
		}
	}
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
	section {
		max-width: 1170px;
		margin: auto;
	}
	.content {
		border: 1px solid rgba(0, 0, 0, 0.26);
		border-radius: 5px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
		padding: 10px;
		margin: auto 7px;
		max-width: 1170px;
	}
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 10px;
	}

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

	.grid {
		max-width: 1170px;
		margin: auto;
		display: grid;
        grid-template-columns: repeat(auto-fill,minmax(275px, 1fr));
	}

	.grid div {
		border: 1px solid rgba(0, 0, 0, 0.26);
		border-radius: 5px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
		padding: 5px;
		margin: 7px;
	}
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
		text-align: center;
	}
</style>
