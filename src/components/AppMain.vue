<script>
import { store } from '../store';
import AppCard from './AppCard.vue';


export default {
    name: 'AppMain',
    data() {
        return {
            store,
        }
    },
    components: {
        AppCard
    }
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