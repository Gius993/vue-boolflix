<template>
  <div id="app">
      <AppHeader @performSearch="search" />
      <AppMain
      :movieCards="movies"
      :seriesCards="series"
      :searching="searchStarted"
      />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>

  import axios from "axios";
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue'
export default {
  name: 'App',
  components: {
    // HelloWorld
    AppHeader,
    AppMain
  },
  computed:{
    computedResults: function (){
      return [...this.movies];
    }
  },
  //array
  data: function(){
    return{
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '4961c6668a6a7f12b27a2f288b02c0eb',
      movies:[],
      series:[],
      allResults:[],
      searchStarted: false
    }
  },
  //funzioni serie e film
  methods:{
    getMovies(apiParams){
      axios
       .get(this.apiUrl + 'movie', apiParams)
       .then((response) =>{
        this.movies = response.data.results;
        // this.allResults = [...this.movies];
        this.searchStarted = true;
       })
 
    },
    getSeries(apiParams){
      axios
       .get(this.apiUrl + 'tv', apiParams)
       .then((response) =>{
        this.series = response.data.results;
        // this.allResults = [...this.series];
        this.searchStarted = true;
       })
       .catch((error) =>{
        console.log("Errore", error);
       }    
       );
       
    },
    
  search: function (searchText){
    const paramsObj = {
      params:{
        api_key: this.apiKey,
        query: searchText,
        language: 'it-IT'
      },
    };
    //chiamata api
    this.getMovies(paramsObj);
    this.getSeries(paramsObj);
  }
  }
};
</script>

<style lang="scss">
 
@import  "./assets/style/setfix.scss";
</style>
