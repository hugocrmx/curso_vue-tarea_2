<template>
  <div class="card">
      <img 
        :src="urlImage"
        :alt="name" 
        style="width:100%">

      <div class="container">
        <div class="card_name"><b>{{ name }}</b></div>         
      </div>

      <div class="card_description">
        {{ description }}
      </div>

      <div class="card_details" v-if="showDetails">
        <a :class="[{'card_details_link' : showDetails}]"  href="https://www.oracle.com/mx/java/">
          READ MORE
        </a>
    </div>

  </div>
</template>

<script>
import {isValidURL} from '@/utils/validations'

export default {
  name: "CardItem",
  props:{
    name:{
      type: String,
      required: true
    },
    description:{
      type: String,
      default: ''
    },    
    urlImage:{
      type: String,
      required: true,
      validator: function(value){
        return isValidURL(value)
      }
    },
    showDetails:{
      type: Boolean,
      default: true
    }
  }
}
</script>

<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 40%;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.container {
  padding: 2px 16px;
}

.card_name{
  font-size: 26px;
  color: #4f4f4f;
  text-align: center;
  padding-top: 20px;
}

.card_description{
  font-size: 16px;
  color: #4f4f4f;
  padding-top: 20px;
  padding-bottom: 15px;
}

.card_details_link{
  color: red;
  text-shadow: 1px 1px 2px black;
}

.card_details{
  padding-bottom: 20px;
  text-align: center;
}

.card_description {
  padding: 0px 30px 30px;
  text-align: justify;
}

</style>