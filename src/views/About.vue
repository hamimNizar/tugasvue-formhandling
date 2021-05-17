<template>
  <div class="about">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Hamim Nizar Y : 205150709111010"/>
    <!-- <div class="container mt-5">
      <div class="row justify-content-center">
        <div class="col-md-6">
            <input v-model="value" type="text" class="form-control">
            <br>
            <p>Value: "{{ value }}"</p>
        </div>
      </div>
    </div> -->
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'About',
  components: {
    HelloWorld
  },
  data() {
      return {
        // value: ''
      }
  }
}
</script>

<style>

</style>