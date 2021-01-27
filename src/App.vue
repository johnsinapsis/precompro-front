<template>
    <div id="app" class="container">
      <Navbar :theme="theme"></Navbar>
      <div class="columns is-mobile">
        <div class="column">
          <Carousel :carousel="carousel"></Carousel>
        </div>
      </div>
      <div class="columns ">
        <div class="column">
          <section>
            <h1 class="is-size-1">{{msg}}</h1>
            <button class="button is-medium is-primary"   @click="changeTheme">
                Cambiar tema
            </button>
          </section>
        </div>
      </div>
      <div class="columns mt-6 is-mobile is-centered">
        <div class="columns ">
          <div class="column" v-for="(card,index) in myCards" :key="index">
            <MyCard :card="card"></MyCard>
          </div>
        </div>
      </div>
      <div class="columns is-mobile is-centered">
        <div class="column pt-3">
        <MyFooter :theme="theme"></MyFooter>
        </div>
      </div>
      
    </div>
</template>

<script>
import Navbar from './assets/components/Navbar'
import image1 from './assets/images/amarillito.jpg'
import image2 from './assets/images/grisesito.jpg'
import image3 from './assets/images/azulito.jpg'
import image4 from './assets/images/greensito.jpg'
import Carousel from './assets/components/Carousel'
import MyCard from './assets/components/MyCard'
import MyFooter from './assets/components/MyFooter'
export default {
  name: 'app',
  data: function(){
    return{
      msg: 'Bienvenidos a mi Landing Page',
      imgSrc:'',
      carousel:[
        {
          name: 'image1',
          original: image1,
          src:''
        },
        {
          name: 'image2',
          original: image2,
          src:''
        },
        {
          name: 'image3',
          original: image3,
          src:''
        },
        {
          name: 'image4',
          original: image4,
          src:''
        }
      ],
      myCards:[
        {
          title: 'john jairo gonzalez',
          image: image1,
          description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris'
        },
        {
          title: 'Adam smith',
          image: image2,
          description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris'
        },
        {
          title: 'Loren Scott',
          image: image3,
          description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris'
        },
        {
          title: 'Jema Winchester',
          image: image4,
          description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris'
        },
      ],
      themes:['light','dark'],
      theme: 'dark'
    }
  },
  components:{
    Navbar,
    Carousel,
    MyCard,
    MyFooter
  },
  methods: {
    changeTheme(){
      //this.$buefy.toast.open("¡Hola, Buefy! Parzibyte.me")
      this.theme = this.theme==='dark' ?  'light' : 'dark'
    },
    loadImages(){
      
      for(var i=0; i < this.carousel.length; i++){
        if(localStorage.getItem(this.carousel[i].name)){
          this.carousel[i].src = localStorage.getItem(this.carousel[i].name)
        }
        else{
          localStorage.setItem(this.carousel[i].name, this.carousel[i].original);
        }
      }
      
    },

    validateTheme: function(name){
      if(name===this.theme)
        return true
      return false
    }
    
  },
  mounted: function(){
    this.loadImages()
  }
}
</script>

<style lang="scss">
$primary-color: black;
$secondary-color: orange;
$auxiliary-color: orangered;


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.navbar-link:not(.is-arrowless)::after {
    border-color:$secondary-color;
}

.navbar-link:hover{
  color: $auxiliary-color;
}

.btn-color{
  background-color: $primary-color;
  color: white;

}


/* footer{
 background-color: whitesmoke;   
} */

</style>
