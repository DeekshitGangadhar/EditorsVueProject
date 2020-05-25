<template>
  <div class="home">
    <AppHeader />
    <HelloWorld msg="Welcome to Your Home page"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import AppHeader from '@/components/Header.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    AppHeader
  }
}
</script>
