<template>
    <div class="github-repo"
        :style="animationDelay">
        <h1><a :href="repo.html_url">{{ repo.name }}</a></h1>
        <p>{{ repo.description }}</p>
        <footer>
            <span>Latest push: {{ latestPush }}</span>
        </footer>
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
        },
        latestPush() {
            const date = new Date(this.repo.pushed_at)
            return `${date.getDate()}.${date.getMonth() + 1}.${date.getFullYear()}`
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
    padding: 2rem 0;

    h1 {
        word-break: break-all;
        padding-bottom: 1rem;
        a {
            color: $theme-dark-red;
        }
    }

    footer {
        color: $theme-gray;
    }
}

</style>
