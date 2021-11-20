<template>
  <div class="card">
	<img v-if="details.poster_path" :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`">
	<!-- Se è presente il details.title allora stampo details.title altrimenti stampo details.name -->
	<h3>{{details.title ? details.title : details.name}}</h3>
	<!-- Se è presente il details.original_title allora stampo details.original_title altrimenti stampo details.original_name -->
	<h4>{{details.original_title || details.original_name}}</h4>
	<div>
		<img v-if="flags.includes(details.original_language)" width="30" :src="require(`../assets/img/${details.original_language}.png`)">
		<img v-else :src="require(`../assets/img/pace.png`)"  width="30">
	</div>
	<div>{{details.vote_average}}</div>
  </div>
</template>

<script>
export default {
	name: "Card",
	props: ['details'],
	data() {
		return {
			flags: ['it', 'en', 'fr']
		}
	},
}
</script>

<style>

</style>