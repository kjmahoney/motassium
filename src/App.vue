<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/>
    <Total/>
    <div class="firebase-data">
      <div v-for="item in items">
       <p><a v-bind:href="item.coffee">{{item.coffee}}</a></p>
     </div>
    </div>
  </div>
</template>

<script>
import Firebase from 'firebase'

import HelloWorld from './components/HelloWorld'
import Total from './components/total'

const config = {
  apiKey: 'AIzaSyDBL7T8sQFweg5_8kJRIR1xW8wzKUhqej4',
  authDomain: 'motassium.firebaseapp.com',
  databaseURL: 'https://motassium.firebaseio.com',
  storageBucket: 'motassium.appspot.com',
  messagingSenderId: '787203548830',
};

const app = Firebase.initializeApp(config)
const db = app.database()
const itemsRef = db.ref('motassium')

export default {
  name: 'App',
  components: {
    HelloWorld,
    Total
  },
  firebase: {
    items: itemsRef
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
