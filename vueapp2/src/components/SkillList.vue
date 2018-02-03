<template>
    <ul class="skills-list">
      <li v-for="skill in skills" :key="skill">{{skill}}</li>
   </ul>
</template>

<script>
export default {
  name: 'SkillList',
  props: {
    skills: {
      type: Array,
      required: true
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
