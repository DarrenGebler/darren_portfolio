<script lang="ts">
    import memoji from '$lib/images/memoji.png';
    import eye from '$lib/images/eye.png';
    import AnimatedElement from "$lib/components/AnimatedElement.svelte";
    import arkose_labs from '$lib/images/arkose_labs.svg';
    import boeing from '$lib/images/boeing.svg';
</script>

<svelte:head>
    <title>Darren's Portfolio</title>
    <meta name="description" content="Darren's Portfolio" />
</svelte:head>

<section>
    <p>Hi, my name is <b>Darren Gebler</b>!</p>
    <p>Welcome to my (simple) portfolio.</p>
    <div>
        <img src={memoji} alt="Memoji" width="120px" id="anchor"/>
        <div id="eyes">
            <img class="eye" src={eye} style="top: -72px; left:39px;" alt="Memoji Eye"/>
            <img class="eye" src={eye} style="top: -72px; left: 65px;" alt="Memoji Eye"/>
        </div>
    </div>

    <div class="scrollwheel">
        <div class='icon-scroll'></div>
    </div>
</section>

<section>
    <AnimatedElement>
        <svelte:fragment slot="animated">
            <p>I'm a <b>Software Engineer</b> based in Brisbane, Australia.</p>
            <p>I've worked for:</p>
            <ul>
                <li><p><a href="https://www.arkoselabs.com/" target="_blank" rel="noreferrer"><img src={arkose_labs} width="100px" style="position: relative; top: 4px;" alt="Arkose Labs"/></a> as an Associate (1 Year)</p></li>
                <li><p><a href="https://www.boeing.com/" target="_blank" rel="noreferrer"><img src={boeing} width="100px" style="position: relative; top: 10px;" alt="Boeing"/></a> as an Intern (1 Year)</p></li>
            </ul>
        </svelte:fragment>
    </AnimatedElement>
</section>

<style>
    section {
        display: grid;
        place-items: center;
        align-content: center;
        min-height: 100vh;
    }

    p {
        height: 10px;
        color: #6887AB;
    }

    li {
        color: #6887AB;
    }

    #eyes, #eyes img {
        position: absolute;
        width: 16px;
    }

    .icon-scroll,
    .icon-scroll:before {
        position: absolute;
        left: 50%
    }

    .icon-scroll {
        width: 20px;
        height: 35px;
        top: 0;
        box-shadow: inset 0 0 0 2px #6887AB;
        border-radius: 12px;
    }

    .icon-scroll:before {
        content: '';
        width: 4px;
        height: 4px;
        background: #6887AB;
        margin-left: -2px;
        top: 8px;
        border-radius: 4px;
        animation-duration: 1.5s;
        animation-iteration-count: infinite;
        animation-name: scroll;
    }

    @keyframes scroll {
        0% {
            opacity: 1;
        }
        100% {
            opacity: 0;
            transform: translateY(23px);
        }
    }

    .scrollwheel {
        position: absolute;
        bottom: 50px;
    }
</style>