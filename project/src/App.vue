
<template>
 <div>
  <h2>Parent: {{carName}}</h2>

  <app-counter v-bind:counterfromapp="counters"></app-counter>


  <app-car
          v-bind:autoName="carName"
          v-bind:carYear="autoyear"

          v-on:namechange="carName= $event"
          v-bind:changeFunc="changeCarNameAudi"


          v-bind:counter="counters"
          v-on:counterUpdated="counters = $event"



  ></app-car>


 </div>
</template>
<script>
 import Car from './car.vue'
 import Counter from './Counter.vue'
 export default {
  name: 'app',
  data () {
   return {
    carName: 'Ford from parent',
    autoyear:2020,
    counters:0
   }
  },
methods:{
  changeCarNameAudi(){
   this.carName='Audi';
  }

},
  components:{
   appCar:Car,
   appCounter:Counter
  }
 }
</script>

<style>

</style>

