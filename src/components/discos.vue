<script setup>
import { ref, defineEmits } from 'vue'


const palabra = ref('')

const emit = defineEmits(['palabraFiltrada'])

function buscar() {
  emit('palabraFiltrada', palabra.value)
}

// lista de Discos
var listaDiscos = [
    {
        id: 1,
        titulo: "Altar",
        artista: "Kehlani",
        portada: "https://i1.sndcdn.com/artworks-nx6qhcZLhQNm-0-t500x500.jpg"
    },
    {
        id: 2,
        titulo: "Rocket Queen",
        artista: "Gun's N' Roses",
        portada: "https://i.ytimg.com/vi/YxW9iekNSek/maxresdefault.jpg"
    },
    {
        id: 3,
        titulo: "Galaxia",
        artista: "Cupido",
        portada: "https://is5-ssl.mzstatic.com/image/thumb/Music124/v4/0c/62/65/0c626580-8c5c-76c4-f3be-dc789116e824/19UMGIM96097.rgb.jpg/1200x1200bf-60.jpg"
    },
    {
        id: 4,
        titulo: "Disturbia",
        artista: "Rihanna",
        portada: "https://i.ytimg.com/vi/wmGjajXDHKo/maxresdefault.jpg"
    }
];


</script>

<template>
    <div id="input">
        <input type="text" v-model="palabra" placeholder="Buscar por titulo" />
        <button @click="buscar">Buscar</button>
    </div>
    <div id="discos">
        <ul>
            <li v-for="disco in listaDiscos" :key="disco.id">
                <h2>{{ disco.titulo }}</h2>
                <h3>{{ disco.artista }}</h3>
                <img :src="disco.portada" alt="portada" />
            </li>
        </ul>
    </div>

    <div>
        <h1>Total de discos: {{ listaDiscos.length }}</h1>
    </div>
</template>

<style>
    ul {
        list-style: none;
    }

    li {
        margin: 10px;
        padding: 10px;
        border: 1px solid black;
    }

    h1 {
        text-align: center;
    }

    input {
        margin: 10px;
        padding: 10px;
        border: 1px solid black;
    }

    input:focus {
        outline: none;
    }

    #input {
        text-align: center;
    }

    img{
        width: 100px;
        height: 100px;
    }

    #discos {
        text-align: center;
    }
</style>