<template>
  <div id="app">
    <CardMain/>
  </div>
</template>

<script>
import CardMain from './components/CardMain.vue';

export default {
  name: 'App',
  components: {
    CardMain,
  }
}
</script>

<style>
  :root {
    /* Primary */
    --very-dark-blue: hsl(233, 47%, 7%);
    --dark-desaturated-blue: hsl(244, 38%, 16%);
    --soft-violet: hsl(277, 64%, 61%);

    /* Neutral */
    --white: hsl(0, 0%, 100%);
    --slightly-transparent-white-main-paragraph: hsla(0, 0%, 100%, 0.75);
    --slightly-transparent-white-stat-headings: hsla(0, 0%, 100%, 0.6)
  }

  #app {
    margin: 0;
    padding: 0; 
  }

  body {
    background-color: var(--very-dark-blue);
  }
</style>
