<template>
  <div class="hello">
    <h1 class="text-3xl text-pink-500 font-bold">{{ msg }}</h1>
    <h1>Boilerplate tailwind CSS</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
