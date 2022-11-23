<!--This is the main place, all other things are will be referenced from here.-->
<template>
  <div id="app">
<!--    template child must have *exactly* one element
**you can put ANYThing you want inside this div, but can only have
this one div.-->
    <h1>Would you rather... </h1>
<!--    you MUST have closed tags when using vue-->
<!--how to include other templates by their name:-->
<!--    another component: suggested by webstorm (looks for uppercase followed by lowercase combos):
This will be replaced by the "WouldYouRather.vue" <div></div> template
** This is useful as it's has all it's own data, rules, logic, etc. can just add it.-->
<!--    <would-you-rather></would-you-rather>-->
<!--    ^^^this is convention because there is no confusion
with any html components, as there are no dashing in html names.-->
<!--    could be written as:
<WouldYouRather></>WouldYouRather>, page will be identical-->

    <!-- start sending data between app.vue and WouldYouRather.vue
    using would-you-rather component (<would-you-rather></>would-you-rather>):
       use v-bind, bind the name of the prop (question) from WouldYouRather.vue:
       the data in question will be "wyrQuestion" from app.vue-->
    <would-you-rather v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    ></would-you-rather>
<!--^^^^Connect the two answers:-->
<!--  answer1 is the name of the prop in the child-->
<!--  wyrAnswer1 is the name of the data in the parent -->

  </div>
  </template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
//  after the set-up, HERE is where you add data:
  data() {
    return {
    wyrQuestion: 'Would you rather never have to take a bath/shower but still always smell nice or never have to get another shot but still be healthy?',
      wyrAnswer1: 'No bathing, but always smell nice.',
      wyrAnswer2: 'No shots, but still be healthy.',
      userSelectionMessage: ''
    //  ^^empty string because nothing has been chosen by the user yet.

    //  app.vue will send the question and two possible answers to WouldYouRather.vue
    // and it will be stored in wouldYouRather.

    //  **Data that a parent component sends to a child component is stored in props
    //  the difference is who sends the data.

      //  Props sent by a parent,
    //    data is stored, generated, or managed internally by a component.
    //
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
