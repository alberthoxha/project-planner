<template>
  <h2>Logo</h2>
  <div class="nav">
    <ul>
    <li>
      <router-link to="/">Home</router-link>
    </li>
      |
      <li>
        <router-link :to="{name: 'About'}">About</router-link>
      </li>
      |
      <li>
        <router-link :to="{name: 'Jobs'}">Jobs</router-link>
      </li>
    </ul>
  </div>
  <div class="but">
    <button @click="redirect">Redirect</button>
    <button @click="back">Go Back</button>
    <button @click="forward">Go Forward</button>
  </div>
  <router-view></router-view>
</template>


<script >
import {RouterLink} from "vue-router";
// const  back = () => {
//   console.log('Back')
// }
export default  {
  methods: {
    redirect() {
      console.log('redirect')
      this.$router.push({name: 'About'})
    },
    back(){
      console.log('back')
      this.$router.go(-1)
    },
    forward(){
      console.log('forward')
      this.$router.go(1)

    }
  },

  }
</script>


<style >
body{
  font-family: Calibri;

}
.nav ul {
  display: flex;
  list-style: none;
  justify-content: center;
  gap: 40px;
  font-size: 18px;

}
.nav ul a {
  color: darkred;
  text-decoration: none;
  padding: 6px 22px;
  outline: none;

}
.nav a.router-link-active {
  color: white;
  background: crimson;
  padding: 6px 22px;
  border-radius: 6px;
  outline: none;
}
.but {
  display: flex;
  justify-content: center;
  gap: 20px

}
button {
  padding: 10px 15px;
  border-radius: 6px;
  border: none;
  cursor: pointer;
}
</style>
