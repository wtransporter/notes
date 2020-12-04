<template>
	<section>
        <base-card>
            <base-error 
                v-if="hasErrors" 
                title="Invalid Input"
                @close="confirmError"
                >
                <template #default>
                    <p>Some fields are empty !</p>
                    <p>Check all fields and try again !</p>
                </template>
                <template #actions>
                    <base-button @click="confirmError">Confirm</base-button>
                </template>
            </base-error>
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
                    <textarea 
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
    </section>

</template>

<script>
	export default {
        inject: ['addNote'],
		data() {
            return {
                title: '',
                hasErrors: false,
            };
        },
        methods: {
            submitData() {
                const enteredDescription = this.$refs.description.value;
                if (this.title.trim() === '' || enteredDescription.trim() === '') {
                    this.hasErrors = true;
                    return;
                }
                this.addNote(this.title, enteredDescription);
                this.resetFields();
            },
            confirmError() {
                this.hasErrors = false;
            },
            resetFields() {
                this.title = '';
                this.$refs.description.value = '';
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