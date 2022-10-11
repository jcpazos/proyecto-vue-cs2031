<template>
    <div class="logos">
        <img alt="Vue logo" v-bind:width="myWidth" v-bind:height="myHeight" src="../assets/logo.png">
        <img alt="Vue logo" v-bind:width="myWidth" v-bind:height="myHeight" src="../assets/logo.png">
        <img alt="Vue logo" v-bind:width="myWidth" v-bind:height="myHeight" src="../assets/logo.png">
    </div>
  </template>
  
  <script>
  export default {
    name: 'LogosComponent',
    props: {
      myWidth: String,
      myHeight: String
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
    .logos {
        margin-left: 40%;
        width:20%;
        justify-content: center;
        background: red;
    }
  </style>
  