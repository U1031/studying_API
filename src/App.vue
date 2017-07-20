<template>
  <div id="app">
    <!--<button v-on:click="searchTerm">Refresh</button>-->
    <div class='total' v-if='user_data.length != 0'>
      <Profile v-bind:profile_img='user_data[0].picture.large'></Profile>
      <ContentIcon v-bind:content_data='user_data[0]'></ContentIcon>
    </div>
  </div>
</template>

<script>
import Profile from './components/Profile';
import ContentIcon from './components/ContentIcon';

export default {
  name: 'app',
  data() {
    return {
      user_data: []
    }
  },
  created() {
    const baseURI = 'https://randomuser.me/api/';
    this.$http.get(`${baseURI}`)
      .then((result) => {
        console.log(result.data.results)
        this.user_data = result.data.results
      })
  },
  methods: {
    searchTerm: function () {
      // using JSONPlaceholder
      const baseURI = 'https://randomuser.me/api/';
      this.$http.get(`${baseURI}`)
        .then((result) => {
          console.log(result.data.results)
          this.user_data = result.data.results
        })
    }
  },
  components: {
    Profile,
    ContentIcon
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 560px;
  text-align: center;
  height: 300px;
  margin : 20px;
  border-radius: 2%;
}

.total {
  border: 0.5px solid lightgray;
  border-radius:2%;
  background-color: lightgray; 
}


</style>
