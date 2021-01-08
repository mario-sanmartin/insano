<template>
    <div>
        <Titulo texto="Consumo de Pastabase" />
        <ul v-for="item in arrayPoto" :key="item.id">
          <li>
            <router-link :to="`/api/${item.id}`">
              {{item.title}}
            </router-link>
          </li>
        </ul>
    </div>
</template>

<script>
import Titulo from '../components/Titulo';
export default {
  components:{
    Titulo
  },
  data(){
    return {
      arrayPoto:[]
    }
  },
  methods:{
   async poringa(){
      try {
      const info = await fetch('https://jsonplaceholder.typicode.com/posts')
      const array = await info.json()
      console.log(array);

      this.arrayPoto = array;
      } catch (error) {
          console.log(error);
      }
    }
  },
  created(){
    this.poringa()
  }

}
</script>

<style>

</style>
