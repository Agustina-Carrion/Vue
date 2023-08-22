<template>
	<div class="card">
		<h3>{{ name }}</h3>
		<p><span>Profession:</span> {{ profession }}</p>
	</div>
</template>

<script>
// export default {
// 	props: ["name", "profession"]
// };
export default {
	props: {
		name: {
			// type: String,
			default: "Lala"
		},
		profession: {
			// type: String,
			default: "Unemployed"
		}
	}
};
</script>

<style scoped>
.card {
	width: 100px;
	border: 2px solid black;
	min-height: 100px;
	background-color: #ccc;
	box-shadow: 10px 10px 10px rgb(0, 0, 0, 0.1);
	padding: 20px;
}

h3 {
	color: red;
}
span {
	font-weight: bold;
}
</style>
