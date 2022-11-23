<template>
  <div class="hello">
<!--    when you add something here, it's
 not added to the page because everything seen
 on the webpage is app.vue, and it's just one h1 element
 **What we do to incorporate components in our page is reference
 them here (in WouldYouRather.vue) in this template-->
  <h2>Please make your choice.</h2>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
