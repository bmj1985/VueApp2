<template>
  <div>

  </div>
</template>

<script>
  export default {
  name: 'Post',
  template: '#post-template',
  props: {
    post: Object,
  },
  data() {
    return {
      show: false,
    }
  },
  methods: {
    toggleShow() {
      this.show = !this.show
    },
})
}
</script>

<style scoped>

</style>
