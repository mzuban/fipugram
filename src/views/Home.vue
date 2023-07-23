<template>
  <div class="row">
    <div class="col-8">
        ... Instagram story!
      <InstagramCard v-for="card in filteredCards" :key="card.url" :info="card" />
    </div>
    <div class="col-4">
      Sidebar
      {{ store.searchTerm }}
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
import InstagramCard from '@/components/InstagramCard.vue'
import store from "@/store"
// ovaj dio je uputa za VueJS kako mora oblikovati InstagramCard komponentu

let cards =[];

cards =[
  {description: "jedan", time: "an hour ago", url:"https://picsum.photos/id/1/400/400" },
  {description: "dva", time: "1 day ago", url:"https://picsum.photos/id/2/400/400" },
  {description: "tri", time: "2 days ago", url:"https://picsum.photos/id/3/400/400" },
  {description: "četiri", time: "3 days ago", url:"https://picsum.photos/id/4/400/400" },

];
//...API -> sve kartice ->cards

export default {
  name: 'home',
  data: function() {
    return{
      cards: cards,
      store,
    };
  },
  computed: {
    filteredCards() {
      //logika koja filtrira cards
      let termin = this.store.searchTerm;
      let newCards = [];

      for (let card of this.cards) {
        if (card.description.indexOf(termin) >= 0) {
          newCards.push(card);
        }
        console.log(newCards);
      }
      return newCards;
    }
  },
  components: {
    InstagramCard,
  },
};
</script>