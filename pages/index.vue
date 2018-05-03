<template>
  <section class="container">
    <div class="ironemes-view">
      <div v-for="ironeme in ironemes" :key="ironeme.id">
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
    const { data } = await axios.get('https://test-d9ac9.firebaseio.com/.json')
    return { ironemes: data }
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
  flex-direction: column-reverse;
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
  div{
    padding: 0 10%;
    width: 100vw;
    height: 50vh;
    
  }
  /*  div:nth-child(3n +2){
    width: 50vw;
    height: 100vh;
    align-self: flex-start;
    padding: 0 10%;
  }
   div:nth-child(3n +3){
    width: 50vw;
    height: 100vh;
    align-self: flex-end;
    padding: 0 10%;
  }*/
}

</style>
