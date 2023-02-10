<script lang="ts">
    import FadeIn from "./lib/FadeIn.svelte";
    import Carousel from 'svelte-carousel';
    const version = '1.11.1';
    const images = ['dark-theme', 'light-theme', 'marine-theme', 'glade-theme', 'pom-theme', 'wist-theme', 'leather-theme'];
</script>
<style lang="scss">
    @import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,400;0,700;1,400;1,700&display=swap');
    div {
        text-align: center;
        width: 60%;
        margin: auto;
        &.wrapper {
            width: 100vw;
        }
        &.head {
            font-size: 3rem;
            font-style: italic;
            font-weight: 700;
            margin-bottom: 1rem;
        }
        &.blurb {
            font-size: 1.2rem;
            font-weight: 400;
            margin-bottom: 1rem;
            line-height: 1.5rem;
        }
        &.img {
            margin-bottom: 1rem;
            img {
                width: 30rem;
                &.logo {
                    width: 10rem;
                }
            }
        }
    }

    a {
        color: white;
        text-decoration: underline;
        transition: 0.2s;
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
            padding: 2rem;
            margin: 0rem;
            &:hover {
                filter: saturate(150%) hue-rotate(360deg) brightness(1.2);
                border: rgb(255, 255, 255) 4px solid;
                border-radius: 100%;
                padding: 0rem;
                margin: 2rem;
            }
        }
    }

    section {
        z-index: 1;
        width: 100vw;
        background-color: rgb(1, 9, 11);
        position: relative;
        margin: 4rem auto 4rem auto;
        
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
            transform: skewY(4deg);
            transform-origin: 100% 0;
        }
        
        &:after {
            bottom: 0;
            transform: skewY(-4deg);
            transform-origin: 100%;
        }
    }
    button {
        background-color: rgb(1, 9, 11);
        border: 1px solid rgb(255, 255, 255);
        border-radius: 0.5rem;
        color: rgb(255, 255, 255);
        font-family: 'Raleway', sans-serif;
        font-size: 2rem;
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
    <section>
        <div class='img'>
            <img src="src/assets/Quill Icon.png" alt="Lexicanter logo" class="logo">
        </div>
    </section>

    <FadeIn>
        <div class='head'>
            Lexicanter
        </div>
    </FadeIn>

    <div class="wrapper" style='height: 8rem'>
        <FadeIn>
            <div class='blurb'>
                <i>Lexicanter</i> is app for constructing languages.
                It was developed and will occasionally be updated by Ethan Ray (known online as Saturnine or Cthethan).<br/>
                It was created in January 2022, and last updated February 2023.
            </div>
        </FadeIn>
    </div>

    <div class="wrapper" style='height: 8rem'>
        <FadeIn>
            <div class='blurb'>
                Version 1.11.1 is available for download for both macOS and Windows.
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
        </FadeIn>
    </div>

    <section>
        <div class="wrapper" style="height: 18rem">
            <FadeIn>
                <div class='img'>
                    <a href="https://www.patreon.com/saturnine_softworks" target="_blank" rel="noreferrer">
                        <img src="src/assets/patreon.png" alt="Patreon icon" class="logo" />
                    </a>
                    <a href="https://discord.gg/uDk2XDhh8K" target="_blank" rel="noreferrer">
                        <img src="src/assets/discord.png" alt="Discord icon" class="logo" />
                    </a>
                </div>
                <div class="blurb">
                    <a href="https://www.patreon.com/saturnine_softworks" target="_blank" rel="noreferrer" class="highlight">
                        Support Lexicanter as a patron!
                    </a>
                    <a href="https://discord.gg/uDk2XDhh8K" target="_blank" rel="noreferrer" class="highlight">
                        Join Saturn's Sojourn on Discord!
                    </a>
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
        <div style='height: 18rem' class='wrapper'>
            <FadeIn>
                <div class='blurb'>
                    I originally started working on this project because I like to keep my language's lexicons formatted nicely,
                    at all times, yet need to keep them organized. Spreadsheets couldn't cut it for me because of aesthetics: keeping
                    a spreadsheet pretty adds unjustifiable amounts of time to their maintenance. On the other hand, word processors
                    lack the functionality for keeping a lexicon organized, and manually maintaining them quickly becomes unfeasible.
                    So, I developed a tool that allows me to keep my lexicons presentable <i>and</i> organized, with the capability
                    to export CSV for spreadsheets as well as plain text that can be brought straight into a word processor. Since then,
                    the feature list of the app has greatly expanded.
                </div>
            </FadeIn>
        </div>
    </section>

</body>