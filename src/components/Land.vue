<template>
<router-link :to="{name: 'LandDetails', params:{naam: singleLand.name.common}}">
<!--  <div class="card border-dark mb-3 d-block mx-auto" style="max-width: 18rem">-->
<!--    <div class="card-header">{{singleLand.title}}</div>-->
<!--      <div class="card-body text-dark">-->
<!--        <h5 class="card-title"> {{singleLand.date}} - {{singleLand.time}}</h5>-->
<!--          <p class="card-text">-->
<!--            {{singleLand.description}}-->
<!--          </p>-->
<!--          <p class="alert-danger"> Locatie: {{singleLand.location}}</p>-->
<!--      </div>-->
<!--  </div>-->
  <section>
    <div class="card" style="width: 18rem;">
            <img :src="singleLand.flags.png" class="card-img-top" alt="...">
            <div class="card-body">
              <p>{{singleLand.name.common}}</p>
            </div>
          </div>

  </section>

  </router-link>
</template>

<script>
export default {
  name: "Land",
  props:{
    singleLand:Object // dit is benoemd in ticket door :event="event"
  },
  // data(){
  //   return{
  //     event:{
  //       category: "concert",
  //       title:"Tomorrow Land",
  //       description:"Festival op de Schorre",
  //       location:"Boom",
  //       date:"August 08 2021",
  //       time:"09:00"
  //     }
  //   }
  // }

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
