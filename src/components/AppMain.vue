<script>
import { store } from '../store';
import AppCard from './AppCard.vue';


export default {
    name: 'AppMain',
    data() {
        return {
            store,
            current: 1
        }
    },
    props: {
        pages: Number
    },
    components: {
        AppCard
    }, 
}
</script>

<template>
    <main>
        <div class="container">
            <div class="row row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-5 g-4 justify-content-center">
                <div v-for="(item, index) in store.characters" :key="index" class="col">
                    <AppCard :item="item" />
                </div>
            </div>
            <div class="my-4 d-flex justify-content-center">
                <a class="btn btn-primary me-4" :class="current === 1 ? 'disabled' : ''" @click.prevent="$emit('prevPage', current = current - 1)">Prev</a>
                <a class="btn btn-primary" :class="current === pages ? 'disabled' : ''" @click.prevent="$emit('nextPage', current = current + 1)">next</a>              
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.ms_card {
    min-height: 180px;

    .bg {
        background-color: rgb(255, 168, 168);
    }
}
</style>