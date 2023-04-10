<template>
  <div id="App">

    <h1>Would You Rather...</h1>
    <WouldYouRather v-bind:question = "wyrQuestion"
    v-bind:answer1 = "wyrAnswer1"
    v-bind:answer2 = "wyrAnswer2"
    v-on:answer-changed="answerChanged"
    >
    </WouldYouRather>
    <p>{{ UserSelectionMessage  }}</p>
  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data () {
    return {
      wyrQuestion: 'Would you rather have your very own house next to your parents house or live with your parents in a house that is twice the size of the one you live in now?',
      wyrAnswer1: 'Own hause next to my parents',
      wyrAnswer2: 'House twice the size of the one you live in now',
      UserSelectionMessage: ''
    }
  },
  methods: {
    answerChanged (choice) {
      this.UserSelectionMessage = `Thanks!  you chose ${choice}`
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
