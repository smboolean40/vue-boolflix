<template>
  <div class="card">
	<h3>{{details.title}}</h3>
	<h4>{{details.original_title}}</h4>
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
	}
}
</script>

<style>

</style>