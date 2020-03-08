<template>
	<li class="li">{{ main }}<br><span class="li__span">{{ desc }}</span></li>	
</template>

<script>
export default {
	props: [
		"main",
		"desc",
	],
};
</script>

<style lang="scss">
.li {
	margin-bottom: .5rem;
	
	&__span {
		opacity: .7;
	}
}

</style>