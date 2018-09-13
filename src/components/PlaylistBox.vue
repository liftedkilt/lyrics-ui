<template>
  <div class="playlistbox">
    <div v-for="song in playlist">
    <a :href="'https://liftedkilt.github.io/' + song.videoID"><div class="v-bar"><div class="v-thumb"><img v-bind:src="'http://images.liftedkilt.xyz/q100/https://i.ytimg.com/vi/' + song.videoID + '/mqdefault.jpg'"></div><div class="v-title">{{ song.videoTitle }}</div></div></a>
  </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'PlaylistBox',
  props: {
    msg: String,
  },
  data() {
    return {
      playlist: [],
    };
  },
  created() {
    axios.get('https://api.liftedkilt.xyz/playlist')
      .then((response) => {
        // JSON responses are automatically parsed.
        this.playlist = response.data.videos;
      });
  },
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.playlistbox {
  margin-top: 10%;
}
img {
  max-width: 50%;
  height: auto;
}
a {
  text-decoration: none;
  color: #42b883;
}

.v-bar {
  display: flex;
  justify-content: flex-start;
  // margin: auto;

  .v-image {
    align-self: flex-start;
  }

  .v-title {
    align-self: center;
    text-align: left;
    color: #2c3e50;
    flex-grow: 1;
  }
}
</style>
