<template>
	<base-card>
		<form @submit.prevent="submitData">
			<div class="form-control">
				<label for="title">Title:</label>
				<input type="text" 
					id="title" 
					name="title" 
					placeholder="Title"
                    v-model="title"
				>
			</div>
			<div class="form-control">
				<label for="description">Description:</label>
				<textarea type="text" 
					id="description" 
					name="description" 
					placeholder="Description"
					rows="5"
                    ref="description"
				></textarea>
			</div>
			<div class="form-control">
				<base-button>Submit</base-button>
			</div>
		</form>
	</base-card>
</template>

<script>
	export default {
        emits: ['add-resource'],
		data() {
            return {
                title: '',
            };
        },
        methods: {
            submitData() {
                const enteredDescription = this.$refs.description.value;
                this.$emit('add-resource', this.title, enteredDescription);
            }
        },
	}
</script>

<style scoped>
	label {
		font-weight: bold;
		display: block;
		margin-bottom: 0.5rem;
		text-align: left;
	}

	input,
	textarea {
		display: block;
		width: 100%;
		font: inherit;
		padding: 0.30rem;
		border: 1px solid #ccc;
		border-radius: 5px;
		resize: vertical;
	}

	input:focus,
	textarea:focus {
		outline: none;
		border-color: #23b0cf;
		background-color: #dcf8ffd0;
	}

	.form-control {
		margin: 1rem 0;
		width: 100%;
	}
</style>