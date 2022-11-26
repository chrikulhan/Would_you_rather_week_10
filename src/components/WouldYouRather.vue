<template>
  <div class="wyr">

<!--    todo add a v-for loop just below to make 3 WouldYouRather components.-->
  <h2 >Would you rather...</h2>

  <h3>{{ question }}</h3>

    <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="choiceMade">
    <label>{{ answer1 }}</label>

    <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="choiceMade">
<!--    write choiceMade method in WouldYouRather (under script below)-->
    <label>{{ answer2 }}</label>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  //You put a type of data in props (so here we'll use a string)vv
  //note String is upper case. (check on vue dev tools to see this is there)
  //**important rule with props: the child component (the thing that has the prop)
  // does not modify, will need to make a new data function (see below)vvv
  props: {
    question: String,
    answer1: String,
    answer2: String,
  },
  //data is a function:
  //reason this is done-- because we could reuse WouldYouRather.vue in an application, (example:
  //asking many questions.)
  data() {
    //will return an object with data in it:
    return {
      //vvv empty string because no choice was made:
      choice: ''
    }
  },
  //make methods for v-on:change="choiceMade"
  methods: {
    choiceMade() {
      // console.log('choice!') **make sure this is working (can see in vue devtools)
      //what this will do is get a message to App.vue
      //can use any name you like, (don't use built in javascript names like click and change),
      //but otherwise, use anything you like.
      //good practice to use a name with a dash in it, because javascript using NO dashes, will not conflict.
      //('answer-changed', list data you want to be sent along to the parent)
      //(this.choice = data, no shower, or no shots in my program)
      //**only the parent component(app.vue) of WouldYouRather would be able to detect and
      //receive this event.
      this.$emit('answer-changed', this.choice)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!--this limits the styles to ONLY WouldYouRather, not App.vue-->
<style scoped>
h3 {
  margin: 40px 0 0;
}

.wyr {
  border: 2px blue;
  background-color: mediumpurple;
}

</style>
