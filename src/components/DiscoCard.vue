<template>
  <div class="prova">
    <div class="card my-3" style="width:11rem; height:20rem">

      <img :src="card.poster" class="card-img-top p-3" alt="image" />

      <div class="card-body">
        <h5 class="card-title text-white">{{card.title}}</h5>
        <p class="card-text text-muted">
          {{card.author}}
          {{card.year}}
        </p>
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DiscoCard",

  props: {
    card: Object,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.card{

  background-color: rgba(42, 58, 71, 1);
  flex-wrap: wrap;

  
}

.prova{
  width: calc(100% / 5 )

}


</style>
