<template>
  <div>
    <main>
      <h1>{{country.name}}</h1>
      <div class="flex">
      <div class="image">
      <img :src="require('@/assets/' + country.image)" alt="">
      </div>
      <div class="desc">
      <h3>
      <b>
      Description
      </b>
      </h3>
        <p>{{country.description}}</p>
      </div>
      </div>
      <div class="moreimages">
      <div v-for="(exp,index) in country.experiences" 
      :key="index">
        <featuredImage :data="exp"></featuredImage>
      </div>
      </div>
    </main>
    
  </div>
</template>

<script>
import featuredImage from '@/components/featuredImage'
import data from './data'
export default {
  data () {
    return {
      destinations:data,
      country:{},
      countryName:this.$route.params.name
    }
  },
  components:{
    featuredImage
  },
created(){
    let ret =  this.destinations.destinations.find(country=>country.name.toLowerCase() === this.countryName)
    this.country = ret;
  },

}
</script>

<style>
.flex{
display: grid;
grid-template-columns: repeat(2,1fr);
grid-gap: 20px;
}
.flex img{
width: 100%;
height: 300px;
object-fit: cover;
}
.moreimages{
display: grid;
grid-template-columns: repeat(4,1fr);
grid-gap: 10px;
}
</style>