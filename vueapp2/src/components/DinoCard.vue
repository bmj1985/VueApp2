<template>
      <div class="profile-card">
          <header class="profile-header" @click="skillsToggle =! skillsToggle">
          <img :src="dino.image"/>
          <h2>{{dino.name}}</h2>
          </header>
          <section class="skills-container" :class="{hidden: skillsToggle}">
          <h4>Skills</h4>
          <SkillList :skills="dino.skills"/>
          </section>
      </div>
</template>

<script>
import SkillList from '@/components/SkillList';

export default {
  name: 'DinoCard',
  components: { SkillList },
  props: {
    dino: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      skillsToggle: true
    };
  }
};
</script>

<style scoped>
section {
  padding: 0 20px 0 20px;
  display: grid;
  grid-template-columns: repeat(auto-fit, x100%);
  grid-gap: 10px;
  margin: 0 auto;
  width: 50%;
}

small {
  color: black;
  font-size: 0.5rem;
  margin-left: 10px;
}

p {
  font-size: 0.8rem;
}

/* Profile Cards */

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
.hidden {
  display: none;
}
</style>
