<template>
  <div class="home">
    <h1
      :style="{'color': color }"
    >
      Contador: {{ contador }}</h1>
    <button @click="aumentar" type="button">Aumentar</button>
    <button @click="disminuir" type="button">Disminuir</button>
  </div>
</template>

<script>
export default {
  data(){
    return {
      contador: 0,
      texto: 'vmodel'
    }
  },
  methods: {
    aumentar(){
      this.contador++;
    },
    disminuir(){
      this.contador--;
    } 
  }, 
  computed: {
    color(){
      if(this.contador < 0){
        return 'red'
      }else{
        return 'blue'
      }
    }
  }
}
</script>
