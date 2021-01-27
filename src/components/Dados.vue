<template>
    <div class="text-center">
        <button class="btn btn-success btn-lg" v-on:click="tirarDados()">Tirar</button>
        <br>
        <img v-bind:src="dadoIzquierda" alt="Dado izquierda">
        <img v-bind:src="dadoDerecha" alt="Dado derecha">
        <h1 v-if="this.numero1 === this.numero2"><span class="badge badge-success">GANASTE</span></h1>
    </div>
</template>

<script>
    export default {
       data() {
           return {
               dadoIzquierda: 'assets/img/dice1.png',
               dadoDerecha: 'assets/img/dice2.png',
               numero1: 1,
               numero2: 2
           }
       },
       methods: {
           tirarDados() {
               this.numero1 = Math.floor(Math.random() * 6) + 1;
               this.numero2 = Math.floor(Math.random() * 6) + 1;
               this.dadoIzquierda = 'assets/img/dice' + this.numero1 + '.png';
               this.dadoDerecha = 'assets/img/dice' + this.numero2 + '.png';
           }
       },
    }
</script>

<style scoped>
    img {
        background-color: red;
        height: 300px;
        width: 300px;
        margin: 30px;
        border-radius: 20px;
    }
   .text-center{
       padding-top: 100px;
       height: 100vh;
       background-color: #e9ecef;
   }
</style>