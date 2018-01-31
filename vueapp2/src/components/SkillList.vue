<template>
<div>
  <section class="skills-container" v-for="skill in skills">
    <h4>Skills</h4>
    <ul class="skills-list">
      <li>{{skill}}.</li>
   </ul>
  </section>
  </div>
</template>

<script>
export default {
  name: 'SkillList',
  props: {
    skills: {
      type: Array
    }
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
.skills-list {
  list-style: none;
}
.hidden {
  display: none;
}
</style>
