<script setup>
import { ref } from 'vue';

defineProps(['variante'])

const contador = ref(0)

function subircontador(numero) {
    contador.value += numero
}
</script>

<template>
    <div class="columna">


        <button @click="subircontador(3)" :class="[variante, variante === 'blue' ? 'p3r' : 'p3']">3</button>


        <button @click="subircontador(2)" :class="[variante, variante === 'blue' ? 'p2r' : 'p2']">2</button>


        <button @click="subircontador(1)" :class="[variante, variante === 'blue' ? 'p1r' : 'p1']">1</button>

        <p>{{ contador }}</p>
    </div>
    

</template>


<style scoped>

.columna {
  width: 260px;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  gap: 0.5px;
}

button {
 width: 100%;
 height: 100px;
 color: white;
 }

.red { background-color: red; }
.blue { background-color: blue; }

/* FORMAS IZQUIERDA */
button.p3 { clip-path: polygon(0 0,100% 0,100% 75%,0 100%); }
button.p2 { clip-path: polygon(0% 50%, 100% 0%, 100% 100%); }
button.p1 { clip-path: polygon(0 0,100% 25%,100% 100%,0 100%); }

/* FORMAS DERECHA (espejo) */
button.p3r { clip-path: polygon(0 0,100% 0,100% 100%,0 75%); }
button.p2r { clip-path: polygon(0 0,100% 50%,0 100%); }
button.p1r { clip-path: polygon(0 25%,100% 0,100% 100%,0 100%); }



</style>