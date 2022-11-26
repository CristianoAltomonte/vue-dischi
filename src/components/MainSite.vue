<template>
  <div>
    <div class="d-flex flex-wrap contenitore-main">
      <DiscoCard v-for="(elem, index) in cards" :key="index" :card="elem" />
    </div>
  </div>
</template>

<script>
import DiscoCard from "./DiscoCard.vue";
import axios from "axios";

export default {
  name: "MainSite",
  components: {
    DiscoCard,
  },

  data() {
    return {
      cards: "",
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.cards = response.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>

.contenitore-main{

    width: 80%;
    margin: 0 auto;
}
</style>