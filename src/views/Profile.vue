<template>
    <div>
        <AppHeader />
        <router-link to="/">
          <input type="button" value="Log-out" id="logout-btn">
        </router-link>
        <h1>This is the profile page</h1>
    </div>
</template>

<script>
import AppHeader from '@/components/Header.vue'

export default {
  name: 'Profile',
  components: {
    AppHeader
  }
}
</script>

<style scoped>
  #logout-btn{
    float: right;
    margin: 20px 30px;
    background-color: #F7444E;
    border-width: 0px;
    border-color: #F7444E;
    color: white;
    padding: 20px;
    font-size: 20px;
    border-radius: 10px;
    cursor: pointer;
  }

  #logout-btn:hover{
    background: none;
    border-width: 2px;
    color: #F7444E;
  }

</style>