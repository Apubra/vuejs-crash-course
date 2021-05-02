<template>
    <div>
        <h1>Hello World</h1>
        <Nwe title="I am prop" />
    </div>
</template>

<script>
import Nwe from "./components/Nwe.vue";
import axios from 'axios';
import Vuex from 'vuex'
export default {
    name: "App",
    components: {
        Nwe,
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
