<template>
    <div>
   
     <container class="buttonDiv tipped">
      <b-button v-on:click="toggleSelect">{{ recommendation.brief }}</b-button>
      <span class="tooltiptext">{{ recommendation.content }}</span>
    </container>
    <container v-if="selected" class="recommendationDetails">
      <h3>{{recommendation.brief}}</h3>
      <p>{{recommendation.content}}</p>
    </container>
    
    


    </div>
</template>

<script>
export default {
  name: 'BootStrap',
  props: {
    msg: String,
  }
}
</script>