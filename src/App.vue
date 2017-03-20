<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <ul>
      <li v-for="(value, key) in emoji">
        {{ String.fromCodePoint(parseInt(value.unicode, 16)) }} {{ key }}
        {{ value }}
        <span v-html="toImage(value.shortname)"></span>
      </li>
    </ul>
  </div>
</template>

<script>
import emojione from 'emojione';
import emoji from 'emojione/emoji.json';

export default {
  name: 'app',
  data () {
    return {
      msg: 'emoji search (comming soon...) 🦄',
      emoji: emoji
    }
  },
  methods: {
    toImage(input) {
      return emojione.toImage(input);
    }
  },
  created() {
    //console.log(emojione);
    console.log(emoji);
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0 auto;
  width: 800px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}
</style>
