<template>
  <div class="hello">
<!--    when you add something here, it's
 not added to the page because everything seen
 on the webpage is app.vue, and it's just one h1 element
 **What we do to incorporate components in our page is reference
 them here (in WouldYouRather.vue) in this template-->
  <h2>Please make your choice.</h2>

<!--    from app.vue would-you-rather component (v-bind) to question
This vvv will display the data on the page:-->
  <h3>{{ question }}</h3>

<!--  from app.vue display the choices that were v-binded to the answers
in the would-you-rather component (would-you-rather) vvv:-->

  <input type="radio"><label>{{ answer1 }}</label>
  <input type="radio"><label>{{ answer2 }}</label>


  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  //You put a type of data in props (so here we'll use a string)vv
  //note String is upper case. (check on vue dev tools to see this is there)
  props: {
    question: String,
    answer1: String,
    answer2: String,
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
