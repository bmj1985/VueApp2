<template>
<section id="profiles-container">
  <h2>Profiles</h2>
  <ul id="profiles">
    <li>
      <div class="profile-card">
          <header class="profile-header" v-for="dino in dinoListData">
          <img :src="dino.image"/>
          <h2>{{dino.name}}</h2>
          </header>
          <SkillList/>
      </div>
    </li>
  </ul>
</section>
</template>

<script>
import SkillList from '../components/SkillList';

export default {
  name: 'DinoCard',
  components: { SkillList },
  props: ['dinoListData']
};
</script>

<style scoped>
.profile-card {
  border-radius: 6px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
  padding: 10px;
  margin: 0 auto 10px auto;
}

.profile-header {
  display: flex;
  flex-flow: row nowrap;
}

.profile-header img {
  width: 100px;
  height: 100px;
  border: 1px solid darkgrey;
  margin: 0 10px 0 10px;
}

.skills-list {
  list-style: none;
}
</style>
