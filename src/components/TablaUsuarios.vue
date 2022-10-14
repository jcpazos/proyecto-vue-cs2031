  <template>
    <div class="table table-dark miTabla">
        <table>
            <tr>
                <th>#</th>
                <th>Username</th>
                <th>Email</th>
            </tr>
            <tr v-for="(usuario, index) in usuarios" :key="index">
                <th>
                    {{ index + 1 }}
                </th>
                <th>
                    {{ usuario.username }}
                </th>
                <th>
                    {{ usuario.email }}
                </th>
            </tr>
        </table>
        <!--<ul>
            <li v-for="usuario in usuarios" v-bind:key="usuario">{{ usuario }}</li>
        </ul>-->
    </div>
    <label for="newUsername">New Username:</label>
    <input v-bind:value="newUsername" v-on:input="onNewUsernameInput" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500  w-20">
    <br><br>
    <button v-on:click="onNewUsernameClick" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Add User!</button>
    <br><br>
    <label for="deleteUsername">Delete username:</label>
    <input v-bind:value="deleteUsername" v-on:input="onDeleteUsernameInput" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500  w-20">
    <br><br>
    <button v-on:click="onDeleteUsernameClick" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Delete User!</button>
  </template>
  
  <script>
  export default {
    name: 'TablaUsuarios',
    props: {
    },
    data () {
        return {
            usuarios: [
                {
                    "username": "jpazos",
                    "email": "jpazos@utec.edu.pe"
                }, 
                {
                    "username": "lhidalgo",
                    "email": "lhidalgo@utec.edu.pe"
                },
                { 
                    "username": "mtorres",
                    "email": "mtorres@utec.edu.pe"
                }
            ],
            'newUsername': '',
            'deleteUsername': ''
        }
    },
    methods: {
            onNewUsernameInput(e) {
                this.newUsername = e.target.value;
            },
            onDeleteUsernameInput(e) {
                this.deleteUsername = e.target.value;
            },
            onNewUsernameClick() {
                this.usuarios.push({ "username": this.newUsername, "email": this.newUsername+"@utec.edu.pe" });
            },
            onDeleteUsernameClick() {
                this.usuarios = this.usuarios.filter((usuario) => usuario.username !== this.deleteUsername);
            }
        }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  .miTabla {
    margin-left: 38%;
  }
  </style>
  