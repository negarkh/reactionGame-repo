<template>
  <p>Reaction Time: {{ scoreResult }} ms</p>
  <p>{{ rank }}</p>
</template>

<script>
export default{
  props: ['scoreResult'],

  data() {
    return{
      rank: null
    }
  },

  mounted() {
    if (this.scoreResult < 250){
      this.rank = 'Awsome Reaction'
    } else if (this.scoreResult < 400){
      this.rank = 'You Are Good'
    } else {
      this.rank = 'At least You Tried'
    }
  }
}
</script>

<style>

</style>
