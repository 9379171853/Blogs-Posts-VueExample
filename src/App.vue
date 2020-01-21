<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1> {{title}} </h1>
    <Navbar />  
    <Blogs />
    <!-- passing props value from pass to childs  -->
    <AllFriends :friends="friends" @delete="deleteFreind"/>
    <OnlineFriends :friends="friends" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import Navbar from "./Navbar"
import AllFriends from "./AllFriends"
import OnlineFriends from "./OnlineFriends"
import Blogs from "./Blogs"

export default {
  name: 'app',
  data(){
    return {
      title : 'My First App , woo :)',
       friends: [
                {name : 'Atul', online: true},
                {name : 'Sunil', online: false},
                {name : 'Raghu', online: true},
                {name : 'Shyam', online: false},
            ]
    }
  },
  methods: {
    deleteFreind(payload){
      console.log(payload)
      this.friends = this.friends.filter(friend =>{
        return friend.name !== payload.name
      })
    }
  },
  components: {
    //HelloWorld
    Navbar,
    OnlineFriends,
    AllFriends,
    Blogs
  }
}
</script>

<style>
h1 {
  color: blue;
  font-weight: normal;
  text-align: center;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
