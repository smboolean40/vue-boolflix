<template>
	<header>
		<form>
			<input type="text" v-model="searchText">
			<button type="submit" @click.prevent="$emit('searching', searchText)">Cerca</button>
		</form>
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