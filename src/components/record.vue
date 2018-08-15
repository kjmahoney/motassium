<template lang="html">
  <div class="c-record">
    <form class="" action="index.html" method="post" v-on:submit.prevent="addItem">
      <input type="text" name="" value="" v-model="newItem.title">
      <input type="text" name="" value="" v-model="newItem.title">
      <input type="submit" class="btn btn-primary" value="addItem">
    </form>
  </div>
</template>

<script>
  export default {
    name: 'Record',
    methods: {
      addItem: function () {
        itemsRef.push(this.newBook);
        this.newBook.title = '';
        this.newBook.author = '';
        this.newBook.url = 'http://';
      },
    },
    data() {
      return {
        newItem: {
          name: '',
          mg: ''
        }
      }
    }
  }
</script>

<style lang="css">
</style>
