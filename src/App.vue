<template>
    <div id="app">
        <Fact v-bind:values="values"/>
    </div>
</template>

<script>
import Fact from './components/Fact.vue'

export default {
  name: 'App',
  components: {
    Fact
  },
  data() {
    return {
        values: {}
    }
  },
  methods: {
        getFact(){
            this.axios.get('http://188.225.47.187/api/cats/random-fact.php')
                .then((response) => {
                    this.values = response.data;
            })
        }
  },
  mounted() {
    this.getFact();
  }
}
</script>

<style>
body {
    background: rgb(238,174,202);
    background: radial-gradient(circle, rgba(238,174,202,1) 0%, rgba(148,187,233,1) 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    margin: 0;
    padding: 0;
    font-family: sans-serif;
    font-size: 18px;
}
</style>
