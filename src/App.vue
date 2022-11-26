<!--This is the main place, all other things are will be referenced from here.-->
<template>
  <div id="app">
<!--    template child must have *exactly* one element
**you can put ANYThing you want inside this div, but can only have
this one div.-->
    <h1>Would you rather?</h1>

    <would-you-rather v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    v-on:answer-changed="answerChanged"></would-you-rather>

    <p>{{ userSelectionMessage }}</p>

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
      questions: [
        {
          id: 0,
          question: '...never have to take a bath/shower but still always smell nice or never have to get ' +
              'another shot but still be healthy?',
          answer1: 'No bathing, but always smell nice.',
          answer2: 'No shots, but still be healthy.',

        },
        {
          id: 1,
          question: '...be a banana or an apple?' ,
          answer1: 'Be a banana',
          answer2: 'Be an apple',
        },
        {
          id: 2,
          question: '...go snorkeling on a reef or camping by a lake?' ,
          answer1: 'Go snorkeling',
          answer2: 'Go camping',
        }
      ],
      userSelectionMessage: ''
    //  ^^empty string because nothing has been chosen by the user yet.

    //  app.vue will send the question and two possible answers to WouldYouRather,
    // and it will be stored in wouldYouRather.

    //  **Data that a parent component sends to a child component is stored in props
    //  the difference is who sends the data.

      //  Props sent by a parent,
    //    data is stored, generated, or managed internally by a component.
    //
    }
  },
  methods: {
    answerChanged(choice) {
      this.userSelectionMessage = `${choice}`
    //  todo bind this choice to each of the 3 questions that are chosen somehow.
    }
  }
}
</script>

<style>

/*to change the color of the whole page:*/
body{
  background: royalblue;
}

/*these styles will be applied to WouldYouRather.vue, but
 WouldYouRather.vue will be scoped, so WouldYouRather styles will only apply to its components*/
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: greenyellow;
}
</style>
