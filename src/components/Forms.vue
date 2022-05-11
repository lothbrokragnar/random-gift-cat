<template>
    <div>
        <form @submit.prevent="getUrl()">
            <div class="form">
                <div class="form--area">
                    <label>Título: </label>
                    <input type="text" v-model="title">
                </div>
                <div class="form--area">
                    <label>Filtro: </label>
                    <select v-model="filter">
                        <option value="" disabled selected>Selecciona tu filtro</option>
                        <option value="blur">Borroso</option>
                        <option value="mono">Monocromático</option>
                        <option value="sepia">Sepia</option>
                        <option value="negative">Negativo</option>
                        <option value="paint">Pintar</option>
                        <option value="pixel">Pixelar</option>
                    </select>
                </div>
                <div class="form--area">
                    <label>Color: </label>
                    <select v-model="color">
                        <option value="" disabled selected>Selecciona tu color</option>
                        <option value="black">Negro</option>
                        <option value="red">Rojo</option>
                        <option value="yellow">Amarillo</option>
                        <option value="blue">Azul</option>
                        <option value="green">Verde</option>
                        <option value="purple">Morado</option>
                        <option value="orange">Naranja</option>
                        <option value="white">Blanco</option>
                    </select>
                    <div class="circle" :style="{backgroundColor: color}"></div>
                </div>
                <div class="form--area">
                    <label>Tamaño: </label>
                    <input type="number" v-model="size">
                </div>
            </div>
            <div class="form--area">
                <button type="submit">Obtener mi gatito</button>
                </div>
        </form>
        <img class="cataas--gif" :src="url" alt="">
    </div>
</template>
<script>
    export default {
        data() {
            return {
                title: '',
                filter: '',
                color: '',
                size: '',
                url: '',

            }
        },
        methods: {
            getUrl() {
                this.url = `https://cataas.com/cat/gif/says/${this.title}?filter=${this.filter}&color=${this.color}&size=${this.size}&width=500&height=300`
            },
        },
    }
</script>
<style>
    .form {
        background: #F0807F;
    }
    .form--area{
        padding: 10px 0;
    }
    .circle{
        border: 1px solid black;
        border-radius: 50%;
        width: 20px;
        height: 20px;
        display: inline-block;
    }
    .cataas--gif{
        border: 3px solid black;
    }
</style>