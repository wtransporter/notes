<template>
	<section>
		<base-card>
			<base-button>All Notes</base-button>
			<base-button mode="btn-flat">Add Note</base-button>
		</base-card>
	</section>
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
import BaseCard from '../ui/BaseCard.vue';
	import SingleNote from './SingleNote.vue';
	export default {
		components: {
			SingleNote,
BaseCard,
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

<style scoped>
	section {
		max-width: 1170px;
		margin: auto;
	}

	.grid {
		margin: auto;
		display: grid;
        grid-template-columns: repeat(auto-fill,minmax(275px, 1fr));
	}

</style>