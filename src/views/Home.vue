<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <div class="container">
      <div class="row">
        <div class="col-12 col-lg-4">
          <Land v-for="land in landen" :key="land.naam" :singleLand="land"></Land>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Land from "@/components/Land.vue";
// import axios from "axios"; dit mag uitgeschakeld wordendoor de TicketService js.
import LandenService from "../services/LandenService";

export default {
  name: "Home",
  components: {
    Land,
  },
  data(){
    return{
      landen: null
    }
  },
  created() { // externe link
    // axios.get('https://my-json-server.typicode.com/Marianna2908/fakejson/events') //endpoint
    //     .then(response =>{
    //   //console.log('events', response.data)
    //       this.events=response.data // met deze date wordt de data gevuld met externe info
    // }).catch(error=> {console.log(error)})
    LandenService.getLanden().then(response =>{
      this.landen = response.data;
      console.log(this.landen)
    }).catch(error =>{console.log(error)})

  }
};
</script>