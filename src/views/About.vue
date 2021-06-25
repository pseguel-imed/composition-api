<template>
  <div class="home">
    <!--<h1
      :style="{'color': color }"
    >Contador: {{ contador }}</h1>-->
    <Titulo :contador="contador" :color="color" />
    <!--<button @click="aumentar" type="button">Aumentar</button>
    <button @click="disminuir" type="button">Disminuir</button>-->
    <hr>
    <input type="text" v-model="texto">
    <p>{{texto}}</p>
    <Btn :textoBoton="'Aumentar'" @accion="aumentar" />
  </div>
</template>

<script>
import Titulo from '../components/Titulo';
import Btn from '../components/Btn';

import { ref, computed } from 'vue';
export default {
  components: {
    Titulo,
    Btn
  },
  setup(){
    const contador = ref(0);
    const texto = ref('');

    const aumentar = () => {
      contador.value ++;
    }
    const disminuir = () => {
      contador.value --;
    }

    const color = computed(() => {
      if(contador.value < 0){
        return 'red'
      }else{
        return 'blue'
      }
    })

    return { contador, aumentar, disminuir, color, texto }
  },
}
</script>