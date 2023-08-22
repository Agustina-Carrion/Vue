<template>
	<div class="cardHolder">
		<PersonCard name="Bob" profession="Student" />
		<PersonCard name="Martha" profession="Influencer" />
	</div>
</template>

<script>
import PersonCard from "./components/PersonCard.vue";
export default {
	components: { PersonCard }
};
</script>

<style scoped>
.cardHolder {
	display: flex;
	gap: 20px;
	flex-wrap: wrap;
	justify-content: center;
}
</style>
