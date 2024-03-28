<script lang="ts">
    import FadeIn from "./lib/FadeIn.svelte";
    import Carousel from 'svelte-carousel';
    const version = '2.1.15';
    const images = ['dark-theme', 'light-theme', 'marine-theme', 'glade-theme', 'pom-theme', 'wist-theme', 'leather-theme'];
</script>
<style lang="scss">
    @import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,400;0,700;1,400;1,700&display=swap');
    @media (max-device-width: 600px) {
        body {
            font-size: 0.7rem;
            line-height: 1.1rem;
        }
        div {
            &.head {
                font-size: 1.5rem;
            }
            &.img {
                img {
                    width: 20rem;
                    &.logo {
                        width: 6rem;
                    }
                    &.icon {
                        width: 4rem;
                    }
                }
            }
            &.wrapper {
                &.small {
                    height: 7rem;
                }
                &.large {
                    height: 14rem;
                }
            }
        }
        button {
            font-size: 1rem;
        }
    }
    @media (min-device-width: 601px) {
        body {
            font-size: 1.2rem;
            line-height: 1.5rem;
        }
        div{
            &.head {
                font-size: 3rem;
            }
            &.img {
                img {
                    width: 30rem;
                    &.logo {
                        width: 12rem;
                    }
                    &.icon {
                        width: 8rem;
                    }
                }
            }
            &.wrapper {
                &.small {
                    height: 8rem;
                }
                &.large {
                    height: 16rem;
                }
            }
        }
        button {
            font-size: 2rem;
        }
    }
    @keyframes hue_rotate {
        0% {
            filter: hue-rotate(0deg);
            border: transparent 4px solid;
            margin: 2rem;
            padding: 3.33rem;
        }
        50% {
            filter: hue-rotate(180deg);
            border: rgb(255, 255, 255) 4px solid;
            margin: 3.33rem;
            padding: 2rem;
        }
        100% {
            filter: hue-rotate(360deg);
            border: transparent 4px solid;
            margin: 2rem;
            padding: 3.33rem;
        }
    }
    div {
        text-align: center;
        width: 66%;
        margin: auto;
        &.wrapper {
            width: 100vw;
        }
        &.head {
            font-style: italic;
            font-weight: 700;
            margin: 2rem auto 1rem auto;
        }
        &.row {
            width: 100vw;
            display: flex;
            flex-direction: row;
            margin: auto;
        }
        &.column {
            display: flex;
            flex-direction: column;
        }
        &.blurb {
            font-weight: 400;
            margin-bottom: 1rem;
        }
        &.centerify {
            width: fit-content;
            margin: auto;
        }
        &.img {
            margin: auto;
            &:has(.logo) {
                margin: 2rem;
                padding: 3.33rem;
                border: transparent 4px solid;
                border-radius: 100%;
                width: fit-content;
                &:hover {
                    animation: hue_rotate 3s infinite;
                }
            }
        }
    }

    a {
        color: white;
        text-decoration: underline;
        transition: 0.33s;
        padding: 0.5rem;
        border-radius: 1rem;
        &.highlight:hover {
            color: black;
            background-color: white;
        }
        img {
            transition: 0.66s;
            border: transparent 4px solid;
            border-radius: 100%;
            padding: 1.33rem;
            margin: 0rem;
            &:hover {
                filter: saturate(150%) hue-rotate(360deg) brightness(1.2);
                border: rgb(255, 255, 255) 4px solid;
                border-radius: 100%;
                padding: 0rem;
                margin: 1.33rem;
            }
        }
        img.beta {
            transition: 0.66s;
            border: transparent 4px solid;
            border-radius: 0%;
            padding: 1.33rem;
            &:hover {
                filter: saturate(150%) hue-rotate(360deg) brightness(1.2);
            }
        }
    }

    section {
        z-index: 1;
        width: 100vw;
        background-color: rgb(1, 9, 11);
        position: relative;
        margin: 3rem auto 3rem auto;
        
        &:before,
        &:after {
            background: inherit;
            content: '';
            display: block;
            height: 50%;
            left: 0;
            position: absolute;
            right: 0;
            z-index: -1;
            -webkit-backface-visibility: hidden; // for Chrome Windows
            backface-visibility: hidden;
        }

        &:before {
            top: 0;
            transform: skewY(3deg);
            transform-origin: 100% 0;
        }
        
        &:after {
            bottom: 0;
            transform: skewY(-3deg);
            transform-origin: 100%;
        }
    }
    button {
        background-color: rgb(1, 9, 11);
        border: 1px solid rgb(255, 255, 255);
        border-radius: 0.5rem;
        color: rgb(255, 255, 255);
        font-family: 'Raleway', sans-serif;
        font-weight: 700;
        margin: 0.5rem;
        padding: 0.5rem 1rem 0.5rem 1rem;
        transition: 0.2s;
        &:hover {
            background-color: rgb(255, 255, 255);
            color: rgb(1, 9, 11);
        }
        & > a {
            color: inherit;
            text-decoration: none;
        }
    }
</style>
<body>
    <section style="margin: -1rem 0 3rem 0;">
        <div class="centerify" style="margin-bottom: -5rem">
            <div class='img'>
                <img src="src/assets/alembic.png" alt="Lexicanter logo" class="logo">
            </div>
        </div>
    </section>

    <FadeIn>
        <div class='head'>
            Lexicanter
        </div>
    </FadeIn>

    <div class="wrapper small">
        <FadeIn>
            <div class='blurb'>
                <i>Lexicanter</i> is an app for constructing languages.
                It was developed and will occasionally be updated by Ethan Ray (known online as Saturnine).<br/>
                It was created in January 2022, and last updated March 2024.
            </div>
        </FadeIn>
    </div>

    <div class="wrapper small">
        <FadeIn>
            <div class='blurb'>
                Version {version} is available for download for both macOS, Windows, and Linux.
            </div>
        </FadeIn>
        <FadeIn>
            <button>
                <a 
                href='https://github.com/Saturnine-Softworks/Lexicanter/releases/download/{version}/Lexicanter-{version}.dmg' 
                target='_blank' rel='noreferrer'>
                    macOS
                </a>
            </button>
            <button>
                <a 
                href="https://github.com/Saturnine-Softworks/Lexicanter/releases/download/{version}/Lexicanter-Setup-{version}.exe"
                target="_blank" rel="noreferrer">
                    Windows
                </a>
            </button>
            <button>
                <a 
                href="https://github.com/Saturnine-Softworks/Lexicanter/releases/download/{version}/Lexicanter-{version}.AppImage"
                target="_blank" rel="noreferrer">
                    Linux
                </a>
            </button>
        </FadeIn>
    </div>
    <br>
    <div class="img">
        <a href="https://discord.gg/uDk2XDhh8K" target="_blank" rel="noreferrer">
            <img src="src/assets/alembic-beta.png" alt="Beta Alembic" class="icon beta" />
        </a>
    </div>
    <div class='blurb'>
        Interested in trying in-development features? Join the beta testers on the Discord!
    </div>
    <br>
    <section>
        <div class="wrapper large">
            <FadeIn>
                <div class='img row'>
                    <div class="column">
                        <a href="https://www.patreon.com/saturnine_softworks" target="_blank" rel="noreferrer">
                            <img src="src/assets/patreon.png" alt="Patreon icon" class="icon" />
                        </a>
                    </div>
                    <div class="column">
                        <a href="https://ko-fi.com/saturnine_softworks" target="_blank" rel="noreferrer">
                            <img src="src/assets/ko-fi.png" alt="Ko-fi icon" class="icon" />
                        </a>
                    </div>
                    <div class="column">
                        <a href="https://discord.gg/uDk2XDhh8K" target="_blank" rel="noreferrer">
                            <img src="src/assets/discord.png" alt="Discord icon" class="icon" />
                        </a>
                    </div>
                </div>
                <div class="blurb row">
                    <div class="column">
                        <a href="https://www.patreon.com/saturnine_softworks" target="_blank" rel="noreferrer" class="highlight">
                            Become a patron!
                        </a>
                    </div>
                    <div class="column">
                        <a href="https://ko-fi.com/saturnine_softworks" target="_blank" rel="noreferrer" class="highlight">
                            Spot me a coffee!
                        </a>
                    </div>
                    <div class="column">
                        <a href="https://discord.gg/uDk2XDhh8K" target="_blank" rel="noreferrer" class="highlight">
                            Join Saturn's Sojourn!
                        </a>
                    </div>
                </div>
            </FadeIn>
        </div>
    </section>

    <div class="wrapper">
        <div class='img'>
            <Carousel
                autoplay={true}
                autoplayInterval={3000}
                loop={true}
                transitionDuration={600}
                transitionTimingFunction={'ease-in-out'}
                transitionMode={'scroll'}
            >
                {#each images as image}
                    <img src="src/assets/{image}.png" alt="Example of a Lexicanter window">
                {/each}
            </Carousel>
        </div>
    </div>

    <section>
        <div class='wrapper large'>
            <FadeIn>
                <div class='blurb'>
                    I originally started working on this project because I like to keep my language's lexicons formatted nicely,
                    at all times, yet need to keep them organized. Spreadsheets couldn't cut it because of aesthetics; on the other hand, 
                    word processors lack the functionality for keeping a lexicon organized So, I developed a tool that allows me to keep
                    my lexicons presentable <i>and</i> organized, with the ability to export CSV for spreadsheets as well as plain text
                    that can be brought straight into a word processor. Since then, the feature list of the app has greatly expanded.
                </div>
            </FadeIn>
        </div>
    </section>

</body>