<template>
  <section id="print-container">
    <div id="print-search"><input v-model="message" placeholder="modifiez-moi"></div>
    <div id="print-area"><h1>{{ message }}</h1></div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import axios from 'axios'

export default {
  components: {
    AppLogo
  },
  data () {
    return {
      message: 'ironème'
      }
    }
}
</script>

<style>
#print-container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;
}

#print-area {
  margin-top: 20vh;
}

#print-area > h1 {
  font-family: Elephant;
  font-size: 20vh;
  text-transform: uppercase;
}

</style>
