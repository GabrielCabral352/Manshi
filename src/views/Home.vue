<template>
  <div>
    <div class="home">
      <h1>Bem-Vindo ao <br> Roberto Manshi </h1>
    </div>
    <Cardinfo 
      text_title = "Tratamento especial"
      text_content ="Lorem ipsum dolor sit amet. Rem esse inventore hic minima voluptatibus vel animi voluptatibus ea eaque deserunt aut delectus obcaecati. Qui maiores placeat aut rerum doloribus sit cumque doloremque ea commodi debitis aut quod voluptatem cum nisi possimus."
      back_color = "black"
      text_color= "white"
      :imgs ="imgs"
    />
  </div>
</template> 
  
<script>
// @ is an alias to /src
import Cardinfo from "../components/Cardinfo.vue"
export default {
  name: 'Home',
  components: {
    Cardinfo,

  },
  data() {
    return {
      imgs: []
    }
  },
  methods: {
    async getImagesBackend() {
      const request = await fetch("http://localhost:3000/imgback")
      const data = await request.json() 
      console.log(data)
    }
  },
  mounted() {
    this.getImagesBackend();
  }
};
</script>


<style scoped src="./home.css" >

</style>