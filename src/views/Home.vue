<template>
  <div class="row">
    <div class="col-8">
        ... Instagram story!
      <InstagramCard v-for="card in cards" :key="card" :info="card" />
    </div>
    <div class="col-4">
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
import InstagramCard from '@/components/InstagramCard.vue'
// ovaj dio je uputa za VueJS kako mora oblikovati InstagramCard komponentu

let cards =[]

cards =[
  {title: "jedan", time: "an hour ago", url:"https://picsum.photos/id/1/400/400" },
  {title: "dva", time: "1 day ago ago", url:"https://picsum.photos/id/2/400/400" },
  {title: "tri", time: "2 days ago", url:"https://picsum.photos/id/3/400/400" },
  {title: "četiri", time: "3 days ago", url:"https://picsum.photos/id/4/400/400" },

];
//...API -> sve kartice ->cards

export default {
  name: 'home',
  data: function(){
    return{
        cards: cards
    }
  },
  components: {
    InstagramCard
  },
};
</script>