<template>
  <div class="container">
	<ul>
		<li v-for="(film, index) in films" :key="index">
			<Card :details="film"/>
		</li>
	</ul>
  </div>
</template>

<script>
import Card from './Card.vue';

export default {
	name: "Films",
	props: ['films'],
	components: {
		Card
	}
}
</script>

<style>

</style>