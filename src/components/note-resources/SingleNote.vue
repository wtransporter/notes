<template>
	<base-card>
		<header>
			<h4>{{ limitTitle }}</h4>
			<span>
				<base-button mode="btn-flat">Delete</base-button>
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
        props: ['title', 'description'],
        computed: {
            limitTitle() {
                if (this.title.length >30) {
                    return this.title.slice(0, 50) + '...';   
                } else {
                    return this.title;
                }
            }
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