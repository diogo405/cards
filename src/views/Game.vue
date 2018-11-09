<template>
	<div class="game">
		<div class="game__card-container">
			<Card v-for="card in cards" :key="card.id"/>
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
      {id: 1, status: "back"}, 
      {id: 2, status: "back"},
      {id: 3, status: "back"},
      {id: 4, status: "back"},
      {id: 5, status: "back"},
      {id: 6, status: "back"},
      {id: 7, status: "back"},
      {id: 8, status: "back"},
      ]
    };
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
