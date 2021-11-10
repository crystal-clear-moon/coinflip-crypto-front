<template>
    <div class="maintenance-body">
        <Nuxt/>
    </div>
</template>

<script>
export default {
    components: {
    }
}
</script>

<style scoped>
.maintenance-body {
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    background: #171721;
    position: relative;
    z-index: 1;
}

.maintenance-body::after {
    content: '';
    position: absolute;
    display: block;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('https://i.imgur.com/o51Sh0V.png');
    background-size: cover;
    background-position: center;
    opacity: 0.1;
    z-index: 2;
}
</style>