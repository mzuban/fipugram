<template>

  <div class="card text-center">
    <div class="card-header text-left">
      {{ info.title }}
    </div>
    <div class="card-body">
      <img class="card-img-top" :src="info.url" alt="neka slika..."/>
    </div>
    <div class="card-footer text-left">
      {{ info.time }}
    </div>
  </div>
</template>

<script>
//JS kod
export default {
  props: ["info"],
  name: 'InstagramCard',
};
</script>

<style lang="scss">
.card {
    margin-bottom: 20px;
}
</style>
