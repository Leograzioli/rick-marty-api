<script>
export default {
    name: 'AppCard',
    props: {
        item: Object
    }
}
</script>

<template>
    <div class="ms_card text-center text-primary">
        <img class="rounded-circle shadow-lg" :src="item.image" :alt="item.name + ' image'">
        <div class="mt-3 p-2 shadow fw-bold bg">
            {{ item.name }}
        </div>
    </div>
</template>

<style lang="scss" scoped>
.ms_card {
    min-height: 180px;

    .bg {
        background-color: rgb(255, 168, 168);
    }
}
</style>