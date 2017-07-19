<template>
  <div id="app">
    <button v-on:click="searchTerm">Refresh</button>
    <div v-if='user_data.length != 0'>
      {{user_data[0].name}}
      <Profile v-bind:profile_img='user_data[0].picture.large'></Profile>
      <ContentIcon></ContentIcon>
    </div>
    <!--<profile v-bind:user_img=''></profile>-->
  </div>
</template>

<script>
import Profile from './components/Profile';
import ContentIcon from './components/ContentIcon';

export default {
  name: 'app',
  data: function () {
    return {
      user_data:[]
    }
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
}
#app button{

  text-align: right;
}
</style>
