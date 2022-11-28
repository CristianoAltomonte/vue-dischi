<template>
  <div>
    <select name="" id="" v-model="valueOptionSelected">
      <option :value="elem" v-for="(elem, index) in arrayGeneri" :key="index">
        {{ elem }}
      </option>
    </select>
    <div class="d-flex flex-wrap contenitore-main">
      <DiscoCard v-for="(elem, index) in funzioneComputed" :key="index" :card="elem" />
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
      arrayGeneri: [],
      valueOptionSelected: "",
    };
  },

  computed: {
    funzioneComputed() {
      if (this.valueOptionSelected == "") {
        return this.cards;
      } else {
        return this.cards.filter((elem) => {
        return elem.genre == this.valueOptionSelected;
        });
      }
    },
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.cards = response.data.response;

        this.cards.forEach((singoloAlbum) => {
          if (!this.arrayGeneri.includes(singoloAlbum.genre)) {
            this.arrayGeneri.push(singoloAlbum.genre);
          }
        });

        this.$emit("emitGeneri", this.arrayGeneri);
      });
  },
};
</script>

<style lang="scss" scoped>
.contenitore-main {
  width: 80%;
  margin: 0 auto;
}
</style>