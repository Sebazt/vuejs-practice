<template>
  <h2>{{customTitle}}</h2>
  <p>{{ start }} = {{ squearecounter }}</p>
  <div class="button-container">
    <button v-on:click="increase">add</button>
    <button v-on:click="decrease">substract</button>
    <button v-on:click="reset">reset</button>
  </div>
</template>

<script>
export default {
  name: 'firstComponent',
  props: {
    title:String,
    start:{
     type:Number,
     //required:true,
     default:7,
     validator(value){
       if(value > 8){
         return true
       }else{
         return false
       }
     }

    }
  },

  data() {
    return {
      counter: this.start
    };
  },

  methods: {
    getSqueareValue() {
      return this.counter * this.counter;
    },
    increase() {
      this.counter = this.counter + 1
    },
    decrease() {
      this.counter--
    },
    reset() {
      this.counter = this.counter * 0
    },
  },

  computed: {
    squearecounter() {
      return this.counter * this.counter;
    },
    customTitle(){
      return this.title ? this.title : 'Counter'
    },

  },
};
</script>

<style>
button {
  background-color: #64bb87;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}

bottom:hover{
  background-color: #5aa57b;
  transition: 0.3s ease-in-out
}
</style>
