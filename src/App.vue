<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppSearch from './components/AppSearch.vue';
import axios from 'axios';
import { store } from './store';

export default {
  data() {
    return {
      store,
      pages: null
    }
  },
  components: {
    AppHeader,
    AppSearch,
    AppMain,
  },
  methods: {
    getAxios(page) {
      this.store.urlApp = "https://rickandmortyapi.com/api/character"
      const parameters = {
        ...this.store.inputKey && { name: this.store.inputKey },
        page
      }

      axios.get(this.store.urlApp, {
        params: parameters
      }).then((resp) => {
        this.store.characters = resp.data.results;
        this.pages = resp.data.info.pages;
        console.log(this.pages);
      })
    }
  },
  created() {
    this.getAxios()
  }
}
</script>

<template>
  <AppHeader />
  <AppSearch @clickBtn="getAxios" />
  <AppMain @nextPage="getAxios" @prevPage="getAxios" :pages="pages"/>
</template>

<style lang="scss">
@use "./styles/general.scss" as *
</style>
