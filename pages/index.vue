<template>
  <section class="container">
    <div>
      <div v-for="ironeme in ironemes" :key="ironeme.id">
          <p>{{ ironeme.text }}</p>
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

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}


</style>
