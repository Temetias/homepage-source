<template>
	<li>{{ main }}<br><span>{{ desc }}</span></li>	
</template>

<script>
export default {
	props: [
		"main",
		"desc",
	],
};
</script>

<style lang="scss" scoped>
li {
	margin-bottom: .5rem;
}

span {
	opacity: .5;
}
</style>