<template>
    <div id="social-media">
        <i class="fa fa-github-square"
            @click="open('https://github.com/Temetias')">
        </i>
        <i class="fa fa-twitter-square"
            @click="open('https://twitter.com/Temetias')">
        </i>
        <i class="fa fa-linkedin-square"
            @click="open('https://www.linkedin.com/in/teemu-karppinen-1174b1139/')">
        </i>
        <i class="fa fa-facebook-square"
            @click="open('https://www.facebook.com/teemu.karppinen.3')">
        </i>
    </div>
</template>

<script>
export default {
    methods: {
        open(url) {
            window.open(url, "_blank")
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

#social-media {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    color: $theme-white;
    font-size: 50px;
    @media only screen and (max-width: $break-small) {
        flex-direction: row;
        justify-content: flex-start;
	}

    & > i {
        cursor: pointer;
        @keyframes grow {
            0% {
                transform: scale(0);
            } 100% {
                transform: scale(1);
            }
        }
        animation: grow .4s;
        animation-delay: 1s;
        animation-fill-mode: backwards;
        transform-origin: center;
        margin: 3px;

        &:nth-child(2) {
            animation-delay: 1.1s;
        }

        &:nth-child(3) {
            animation-delay: 1.2s;
        }

        &:nth-child(4) {
            animation-delay: 1.3s;
        }

        transition: transform .4s;
        &:hover {
            transform: scale(1.2);
            @media only screen and (max-width: $break-small) {
                transform: none;
            }
        }
    }
}
</style>