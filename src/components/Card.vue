<template>
	<div :class="[{'card--face': card.status == 'face'}, 'card']">
		{{card.name}}
	</div>
</template>

<script>
export default {
  name: "card",
  props: {
    card: Object
  }
};
</script>

<style lang="scss">
.card {
  background: black;
  width: calc(100% / 4 - 50px);
  height: 200px;
  margin-top: 50px;
  cursor: pointer;
}
.card--face {
  background: yellow;
}
</style>
