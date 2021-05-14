<template>
  <div class="box">
    <img :src="require('@/assets/' + data.image)" alt="">
    <h2 class="name">{{data.name}}</h2>
    <p>{{data.description}}</p>
  </div>
</template>

<script>
export default {
  props: {
      data:{
          type:Object,
          required: true
      }
  },

}
</script>


<style>

.box{
    background: whitesmoke;
    padding: 20px;
}
.box img{
    height: 50%;
width: 100%;}
.name{
color: red;}

</style>