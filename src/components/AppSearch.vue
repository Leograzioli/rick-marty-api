<script>
import { store } from '../store';
export default {
    name: 'AppSearch',
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="text-center mb-5">
        <input type="text" @keyup.enter="$emit('clickBtn')" placeholder="Search Character Name"
            class="text-primary fw-bold" v-model="store.inputKey">
        <button @click="$emit('clickBtn')" class="btn btn-primary ms-2">Send!</button>
    </div>
</template>

<style lang="scss" scoped>
input {
    border: none;
    border-radius: 20px;
    padding: 0.5rem 1rem;
}
</style>