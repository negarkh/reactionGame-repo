<template>
  <p>Reaction Time: {{ scoreResult }} ms</p>
  <p class="rank">{{ rank }}</p>
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
      this.rank = 'Awesome Reaction!'
    } else if (this.scoreResult < 400){
      this.rank = 'Hmm.. You Are Good!'
    } else {
      this.rank = 'OK.. At Least You Tried'
    }
  }
}
</script>

<style>
  .rank {
  font-size: 1.4em;
  color: purple;
  font-weight: bold;
  }
</style>
