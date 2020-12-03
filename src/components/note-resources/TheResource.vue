<template>
	<section>
		<base-card>
			<base-button 
				@click="setActiveTab('stored-notes')"
				:mode="selectedSingleTab"
				>All Notes</base-button>
			<base-button 
				@click="setActiveTab('new-resource')"
				:mode="selectedAddTab">Add Note</base-button>
		</base-card>
	</section>

	<keep-alive>
		<component :is="activeTab"></component>
	</keep-alive>

</template>

<script>
	import StoredNotes from './StoredNotes.vue';
	import NewResource from './NewResource.vue';

	export default {
		components: {
			StoredNotes,
			NewResource,
		},
		data() {
			return {
				activeTab: 'stored-notes',
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
			addResource(title, description) {
				const newNote = {
					id: new Date().toISOString(),
					title: title,
					description: description
				};

				this.notes.unshift(newNote);
			},
			setActiveTab(name) {
				this.activeTab = name;
			},
			removeResource(id) {
				const foundItem = this.notes.findIndex(item => item.id === id);

				this.notes.splice(foundItem, 1);

			}
		},
		computed: {
			selectedAddTab() {
				return this.activeTab === 'stored-notes' ? 'btn-flat' : 'btn-primary';
			},
			selectedSingleTab() {
				return this.activeTab === 'new-resource' ? 'btn-flat' : 'btn-primary';
			},

		},
		provide() {
			return {
				notes: this.notes,
				addNote: this.addResource,
				removeNote: this.removeResource,
			};
		}
	}
</script>

<style scoped>
	section {
		max-width: 1170px;
		margin: auto;
	}
</style>