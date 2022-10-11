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
            ]
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
  