<template>
  <div id="app">

    <HeaderSite/>
    <MainSite/>
    
  </div>
</template>

<script>
import MainSite from "./components/MainSite.vue";
import HeaderSite from "./components/HeaderSite.vue";

export default {
  name: "App",
  components: {
    MainSite,
    HeaderSite,
    
  },
  
};
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#app {

  background-color: rgba(24, 45, 62, 1);
  height: 100vh;
  
}
</style>
