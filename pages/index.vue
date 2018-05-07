<template>
  <section class="container">
    <div class="ironemes-view">
      <div v-for="(ironeme, index) in ironemes" :key="index">
          <h1>{{ ironeme.text }}</h1>
          <p>{{ ironeme.user.name }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import axios from 'axios'

export default {
  components: {
    AppLogo
  },
  async asyncData () {
    const { data } = await axios.get('https://test-d9ac9.firebaseio.com/.json?orderBy=%22$key%22&limitToLast=6')
    return { ironemes: data }
  },
  methods: {
    test : function () {
      console.log(this.ironemes);
    }
  },
  beforeMount() {
    this.test()
  }
}
</script>

<style lang="scss">
* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.ironemes-view {
  display: flex;
  flex-wrap: wrap;
  align-content: stretch;
  justify-content: center;
  align-items: center;
  h1 {
    font-family: Elephant;
    text-transform: uppercase;
  }
  p{
    font-family: Graebenbach;
  }
  div{
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column ;
  }
  div:nth-child(3n +1){
    padding: 0 10%;
    width: 100vw;
    height: 50vh;
    
  }
    div:nth-child(3n +2){
    width: calc(100% * (1/2) - 10px - 1px);
    height: 50vh;
    align-self: flex-start;
    padding: 0 10%;
    }
   div:nth-child(3n +3){
    width: 50vw;
    height: 50vh;
    align-self: flex-end;
    padding: 0 10%;
  }
}

</style>
