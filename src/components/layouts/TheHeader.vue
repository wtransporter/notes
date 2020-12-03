<template>
    <header>
        <h3>{{ title }}</h3>
    </header>
</template>

<script>
export default {
  props: {
    title: String
  }
}
</script>

<style scoped>
    header {
        font-size: 32px;
        height: 80px;
        background-color: var(--primary);
        display: flex;
        align-items: center;
        justify-content: center;
    }
    header h3 {
        margin: 0;
        color: white;
    }
</style>
