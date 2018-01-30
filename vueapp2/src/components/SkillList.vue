<template>
  <section class="skills-container hidden">
    <h4>Skills</h4>
    <ul class="skills-list" v-for="skill in skillListData">
      <li>{{skill}}</li>
   </ul>
  </section>
</template>

<script>
export default {
  name: 'SkillList',
  props: ['skillListData']
};
</script>

<style scoped>
.skills-list {
  list-style: none;
}
.hidden {
  display: none;
}
</style>
