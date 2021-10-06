<template>
	<header>
		<input type="text" v-model="searchText">
		<button @click="$emit('searching', searchText)">Cerca</button>
	</header>
</template>

<script>
export default {
	name: "Header",
	data() {
		return {
			searchText: ""
		}
	}
}
</script>

<style>

</style>