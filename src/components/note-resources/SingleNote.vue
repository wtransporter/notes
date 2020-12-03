<template>
	<base-card>
		<header>
			<h3>{{ title }}</h3>
			<span>
				<base-button mode="btn-flat">Delete</base-button>
			</span>
		</header>
		<p>
			{{ description }}
		</p>
        <nav class="left">
            <a href>Details</a>
        </nav>
	</base-card>
</template>

<script>

	export default {
		props: ['title', 'description'],
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