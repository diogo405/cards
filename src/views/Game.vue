<template>
	<div class="game">
		<div class="game__card-container">
			<Card v-for="card in cards" :key="card.id" :card="card"/>
		</div>
	</div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  name: "game",
  components: {
    Card
  },
  data() {
    return {
      // prettier-ignore
      cards: [
      {id: 1, status: "back", name: "Card 1"}, 
      {id: 2, status: "back", name: "Card 2"},
      {id: 3, status: "back", name: "Card 3"},
      {id: 4, status: "back", name: "Card 4"},
      {id: 5, status: "back", name: "Card 5"},
      {id: 6, status: "back", name: "Card 6"},
      {id: 7, status: "back", name: "Card 7"},
      {id: 8, status: "back", name: "Card 8"},
      ]
    };
  },
  methods: {
    toggleCard(cardIndex) {
      let card = this.cards[cardIndex];
      let currrentCardStatus = card.status;
      let newStatus = currrentCardStatus == "face" ? "back" : "face";
      card.status = newStatus;
      // prettier-ignore
      setTimeout(() => {
      	console.log('Turn back:', cardIndex);
      	this.toggleCard(cardIndex)
      }, 1000);
    }
  },
  mounted() {
    // prettier-ignore
    setInterval(() => { 
      let cardIndex = Math.floor(Math.random() * this.cards.length);
      console.log('Turn face:', cardIndex);
      this.toggleCard(cardIndex); 
    }, 1000);
  }
};
</script>

<style lang="scss">
.game {
}
.game__card-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 5%;
}
</style>
