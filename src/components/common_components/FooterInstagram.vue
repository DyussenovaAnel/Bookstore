<template>
<div class="item m-1">
  <div class="grid">
      <div>
          <div></div>
      </div>
  </div>
</div>

</template>

<script>
export default {
  name: 'BookDigital',
  props: ['product'],
  methods: {
    details (title) {
      this.$router.push('/products/' + title)
    }
  }
}
</script>

<style scoped>

</style>
