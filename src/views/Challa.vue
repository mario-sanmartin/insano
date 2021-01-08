<template>
  <div>
    <h1>Mussollini</h1>
    <h2>Parametro : {{this.$route.params.id}}</h2>
    <h2>Titulo {{cosita.title}}</h2>
    <h3>{{cosita.body}}</h3>
  </div>
</template>

<script>
export default {
  data(){
    return{
      cosita: {}
    }
  },
  methods:{
    async cargarCosita(){
        try {
      const carga = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
      const nacionalSocialismo = await carga.json()

      this.cosita = nacionalSocialismo;
        } catch (error) {
          console.log(error);
        }
    }
  },
      created(){
            this.cargarCosita()
        }
}
</script>

<style>

</style>
