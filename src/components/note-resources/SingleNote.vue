<template>
	<base-card>
        <base-error 
            v-if="confirmDelete"
            title="Confirm delete ?"
            @close="cancelAction"
        >
            <template #default>
                <p>Are you sure ?</p>
            </template>
            <template #actions>
                <base-button @click="confirmAction">Delete</base-button>
                <base-button @click="cancelAction">cancel</base-button>
            </template>
        </base-error>
		<header>
			<h4>{{ title }}</h4>
			<span>
				<base-button 
                    @click="deleteItem"
                    mode="btn-flat"
                >
                    Delete
                </base-button>
			</span>
		</header>
        <nav class="left">
            <p>
                {{ description }}
            </p>
            <a href>Details</a>
        </nav>
	</base-card>
</template>

<script>

	export default {
        props: ['title', 'description', 'id'],
        inject: ['removeNote'],
        data() {
            return {
                confirmDelete: false,
            };
        },
        methods: {
            deleteItem() {
                this.confirmDelete = true;
            },
            confirmAction() {
                this.confirmDelete = false;
                this.removeNote(this.id);
            },
            cancelAction() {
                this.confirmDelete = false;
            },
        }
	}
</script>

<style scoped>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 10px;
	}

    .left {
        text-align: left;
        padding: 0 10px;
    }

    a {
        text-decoration: none;
        color: #cc6b10;
    }

    a:hover {
        color: #c58e5a;
    }

</style>