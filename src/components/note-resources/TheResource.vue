<template>
	<section>
		<base-card>
			<base-button 
				@click="setActiveTab('single-note')"
				:mode="selectedSingleTab"
				>All Notes</base-button>
			<base-button 
				@click="setActiveTab('new-resource')"
				:mode="selectedAddTab">Add Note</base-button>
		</base-card>
	</section>
	<section class="grid" v-if="activeTab === 'single-note'">
		<single-note v-for="note in notes" :key="note.id"
			:id="note.id"
			:title="note.title"
			:description="note.description"
		>
		</single-note>
	</section>
	<section v-else>
		<new-resource></new-resource>
	</section>
</template>

<script>
import BaseCard from '../ui/BaseCard.vue';
	import SingleNote from './SingleNote.vue';
	import NewResource from './NewResource.vue';
	export default {
		components: {
			SingleNote,
			BaseCard,
			NewResource,
		},
		data() {
			return {
				activeTab: 'single-note',
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
		},
		methods: {
			setActiveTab(name) {
				this.activeTab = name;
			}
		},
		computed: {
			selectedAddTab() {
				return this.activeTab === 'single-note' ? 'btn-flat' : 'btn-primary';
			},
			selectedSingleTab() {
				return this.activeTab === 'new-resource' ? 'btn-flat' : 'btn-primary';
			},

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