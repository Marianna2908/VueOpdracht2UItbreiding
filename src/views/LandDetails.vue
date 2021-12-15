<template>
  <div v-if="land.name" >
    <div class="container">
      <div class="row">
        <div class="col-12 col-lg-6">
            <img :src="land.flags.png" class="card-img-top" alt="...">
          <h2>hoofdstad: {{land.capital[0]}}</h2>
        </div>
        <div class="col-12 col-lg-6">
          <h3> Land: {{land.name.common}}</h3>
          <h4> Land Area {{land.area}}</h4>
          <p> Aantal inwoners: {{land.population}}</p>
          <p> Lands Regio: {{land.region}}</p>
          <br>
          <iframe :src="land.maps.googleMaps" width="500" height="500"></iframe>
        </div>
      </div>
    </div>
  </div>
</template>
<script>

import LandenService from "../services/LandenService";

export default {
  name: "LandDetails",
  props:["naam"],
  data(){
    return{
      land:null,
    }
  },

  created() {
    LandenService.getLand(this.naam).then(response => {
      console.log('land',response.data)
      this.land = response.data[0];
    }).catch(error => {
      console.log(error)
    })
  }
}
</script>

<style scoped>

</style>