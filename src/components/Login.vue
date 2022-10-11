<template>
    <div class="login content-center">
      <label for="username">Username: </label>
      <input v-bind:value="username" v-on:input="onUsernameInput" name="username" id="username" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500  w-20">
      <br><br>
      <label for="password">Password: </label>
      <input v-bind:value="password" v-on:input="onPasswordInput" name="password" id="password" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500  w-20">
      <br><br>
      <button v-on:click="onLogin" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Login!</button>
      <br><br>
      <div v-if="success && loginAttempt" id="success">Success!</div>
      <div v-if="!success && loginAttempt" id="fail">Incorrect username or password</div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LoginComponent',
    props: {
    },
    data () {
        return {
            username: "",
            password: "",
            success: false,
            loginAttempt: false
        }
    },
    methods: {
        onUsernameInput(e) {
            this.loginAttempt = false;
            this.username = e.target.value;
        },
        onPasswordInput(e) {
            this.loginAttempt = false;
            this.password = e.target.value;
        },
        onLogin() {
            const url = "http://localhost:5000/login/async";

            const body = {
                "username": this.username,
                "password": this.password
            };

            fetch(url, {
                method: "POST",
                body: JSON.stringify(body),
                headers: {
                    "Content-Type": "application/json"
                }
            }).then((resp) => resp.json())
            .then((data) => {
                this.loginAttempt = true;
                //operador ternario (ternary operator)
                // this.success = data.success ? true : false;

                this.success = data.success;
            });
        }
    }
  }

  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
    #success {
        color: green;
    }

    #fail {
        color: red;
    }
  </style>
  