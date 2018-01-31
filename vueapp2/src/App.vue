<template>
  <div id="app">
    <TheHeader/>
    <main>
      <section id="profiles-container">
      <h2>Profiles</h2>
      <ul id="profiles">
        <DinoCard :dinos="dinoProfiles"/>
      </ul>
    </section>
    </main>
    <TheFooter/>
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
      dinoProfiles: [],
      skillsList: []
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
          console.log(response);
          this.dinoProfiles = response;
        });
    }
  }
};
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1b997a;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}

main {
  grid-row: 2/3;
}

section {
  padding: 0 20px 0 20px;
  display: grid;
  grid-template-columns: repeat(auto-fit, x100%);
  grid-gap: 10px;
  margin: 0 auto;
  width: 50%;
}
</style>
