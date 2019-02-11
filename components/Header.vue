<template>
    <div id="header">
        <div class="header__filler"></div>
        <svg viewBox="0 0 500 500" preserveAspectRatio="xMinYMin meet" id="wave__container">
            <path d="M0,100 C150,200 350,0 500,100 L500,00 L0,0 Z" id="wave"></path>
        </svg>
        <div class="header__text">
            <h1>Hello.</h1>
            <p>My name is Teemu Karppinen. I'm a Full Stack Developer.</p>
        </div>
    </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import "@/layouts/theme.scss";

#header {
    color: $theme-white;
    width: 100%;
    height: 70vh;
    pointer-events: none;
}

.header {
    &__text {
        position: absolute;
        top: 50%;
        left: 10%;
        transform: translateY(-50%);
        @keyframes fade {
            0% {
                opacity: 0;
            } 100% {
                opacity: 1;
            }
        }

        & > h1 {
            font-size: 8vw;
            @media only screen and (max-width: $break-small) {
                font-size: 12vw;
            }
            animation: fade .7s;
            animation-delay: .3s;
            animation-fill-mode: both;
        }

        & > p {
            font-size: 3vw;
            @media only screen and (max-width: $break-small) {
                font-size: 6vw;
            }
            animation: fade .7s;
            animation-delay: .6s;
            animation-fill-mode: both;
        }
    }

    &__filler {
        background-color: $theme-red;
        height: calc(90vh - 40vw);
        min-height: 200px;
    }
}

#wave {
    stroke: none;
    fill: $theme-red;
    
    &__container {
        filter: drop-shadow(2px 7px 2px rgba(0, 0, 0, .7));
    }
}
</style>
