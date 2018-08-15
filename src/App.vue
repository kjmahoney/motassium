<template>
  <div class="c-items">
    <div v-for="item of items">
      {{item.name}} : {{ item.milligrams }}
    </div>
    <div v-for="date of dates">
      {{date.date}} : {{ date.totalMg }}
    </div>
  </div>
</template>

<script>
import Firebase from 'firebase'
import Record from './components/record'

const config = {
  apiKey: "AIzaSyDBL7T8sQFweg5_8kJRIR1xW8wzKUhqej4",
  authDomain: "motassium.firebaseapp.com",
  databaseURL: "https://motassium.firebaseio.com",
  projectId: "motassium",
  storageBucket: "motassium.appspot.com",
  messagingSenderId: "787203548830"
};

const app = Firebase.initializeApp(config)
const db = app.database()

export default {
  data() {
    return {
      items: {},
      dates: {},
    }
  },

  firebase: {
    items: {
      source: db.ref('items'),
      // Optional, allows you to handle any errors.
      cancelCallback(err) {
        console.error(err);
      }
    },
    dates: {
      source: db.ref('dates'),
      cancelCallback(err) {
        console.error(err);
      }
    }
  }
}

</script>

<style>
  .c-items{
    background-color: red;
  }
</style>
