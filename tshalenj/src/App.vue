<template>
  <div>
     <NavBar />
  <main>
    <router-view />
  </main>
  <footer-comp/>
  </div>
 
</template>
<script>
import NavBar from './components/NavBar.vue';
import FooterComp from './components/FooterComp.vue'
export default {
  components: {
    NavBar,
    FooterComp
  }
}
</script>

<style>

</style>
