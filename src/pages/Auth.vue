<template >
  <div class="parentAuth">
  <div class="auth">
    <router-view></router-view>
  </div>
  </div>
</template>


<script>
  import {defineComponent} from 'vue'
  import Login from '../components/Login'
  import Registration from "../components/Registration";

  export default defineComponent({
    name: 'Auth'
  })
</script>


<style>

</style>
