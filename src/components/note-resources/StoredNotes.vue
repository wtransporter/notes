<template>
	<section class="grid">
		<single-note v-for="note in notes" :key="note.id"
			:id="note.id"
			:title="note.title"
			:description="note.description"
		>
		</single-note>
	</section>
</template>

<script>
	import SingleNote from './SingleNote.vue';

	export default {
		components: {
			SingleNote,
		},
		inject: ['notes'],
	}
</script>

<style scoped>
	.grid {
		margin: auto;
		display: grid;
        grid-template-columns: repeat(auto-fill,minmax(275px, 1fr));
	}
</style>