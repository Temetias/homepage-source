<template>
    <div class="github-repo"
        :style="animationDelay">
        <h1><a :href="repo.html_url">{{ repo.name }}</a></h1>
        <p>{{ repo.description }}</p>
    </div>    
</template>

<script>
export default {
    props: [
        "index",
        "repo"
    ],
    computed: {
        animationDelay() {
            return { "animation-delay": `${this.index / 8}s` }
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

.github-repo {
    @keyframes fade {
        0% {
            opacity: 0;
        } 100% {
            opacity: 1;
        }
    }
    animation: fade .5s;
    animation-fill-mode: both;
}

</style>
