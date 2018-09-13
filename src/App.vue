<template>
  <div id="app">
    <nav>
      <ul class="nav-bar">
        <li id="home"><a href="/"><h1>Home</h1></a></li>
        <li id="lyrics"><a href="liftedkilt.github.io"><h1>Lyrics</h1></a></li>
      </ul>
    </nav>

  <PlaylistBox />

  </div>
</template>

<script>
import PlaylistBox from './components/PlaylistBox.vue';

export default {
  name: 'app',
  components: {
    PlaylistBox,
  },
};
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

a {
  text-decoration: none;
  color: #42b883;
}

.nav-bar {
  display: flex;
  justify-content: flex-start;
  border-bottom: 1px solid black;
  margin: auto;
  background-attachment: fixed;

  li {
    list-style-type: none;
    text-align: left;

  }
  #home {
    flex: 1;
  }
  #lyrics {
    flex: 3;
  }
}

@media all and (max-width: 600px) {

  .nav-bar {
    flex-wrap: wrap;
  }

  .nav-bar > li {
    flex-basis: 50%;
  }
}

</style>
