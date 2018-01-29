<template>
  <div id="app">
    <DinoCard :dinoListData="listingData" :skillListData="skillsData"/>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader';
import DinoCard from './components/DinoCard';
import TheFooter from './components/TheFooter';

export default {
  name: 'App',
  components: { TheHeader, DinoCard, TheFooter },
  data() {
    return {
      apiURL: '../static/dinosaurs.json',
      listingData: [],
      skillsData: []
    };
  },
  mounted() {
    this.getListings();
  },
  methods: {
    getListings() {
      fetch(this.apiURL)
        .then(response => response.json())
        .then(response => {
          this.listingData = response;
          this.skillsData = this.listingData.map(dinoObject => {
            return dinoObject.skills;
          });
          return this.skillsData;
        });
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
