<template>
    <Fact v-bind:values="values"/>
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

#app {
    
    background-color: #eff5f8;
    border-radius: 20px;
    box-shadow: 0px 0px 15px 0px rgba(50, 50, 50, 0.5);
    position: relative;
    padding: 30px 30px 0;
    margin: auto;
}
</style>
