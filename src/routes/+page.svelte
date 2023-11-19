<script>
	import Contacts from "../components/Contacts.svelte";
	import Greeter from "../components/Greeter.svelte";
	import Nav from "../components/Nav.svelte";
	import Slide from "../components/Slide.svelte";
	import StackSlide from "../components/StackSlide.svelte";

    let navShow = false;
    let slideShow= false;
    let position;
    let textAbout = "Graduated from St. Petersburgs Petrovskiy college, famous for its ahead of time IT studying practices also known as Russian MIT. Seasoned with working experience in MIA IT & cyber security structures and \"P&G\" SS Leader position."
    let textSpecs = "Prepare to be blown away by the ultimate tech virtuoso! Behold a master of system administration, an unstoppable force in info sec and cybersec, a wizard of front-end and back-end development, a maestro of network ops, a guru of server hardware, and a genius of PC software. I possess an unrivaled skill set that will leave you in awe. Experience impenetrable system security, mesmerizing website functionality, flawless network operations, and mind-blowing hardware and software solutions.";
    let textContacts = 'Contatcs';
</script>

<div class="main-container {slideShow ? 'main-container-top' : ''}">
    <div class="greet-nav-wrapper">
        <div class="greeter {navShow ? 'greeter-left' : ''}"
        on:click={()=>{navShow=!navShow; slideShow=false; position=''}} 
        on:keydown={()=>{navShow=!navShow}} 
        aria-hidden="true">
            <Greeter />
        </div>
        <div class="{navShow ? 'nav slide-right' : 'nav-hidden slide-left'}">
            <Nav bind:position={position}
            bind:show={slideShow}/>
        </div>
    </div>
    {#key position}
    <div class=" {slideShow ? 'content slide-top' : 'slide-bottom'}">
        {#if position == 'about'}
        <Slide text={textAbout} />
        {:else if position == 'specs'}
            <Slide text={textSpecs}/>
        {:else if position == 'stack'}
            <div class="stack-slide">
                <StackSlide/>
            </div>
        {:else if position == 'contacts'}
            <div class="contact-slide">
                <Contacts />
            </div>
        {/if}
    </div>
    {/key}
</div>


<style>
    .main-container{
        font-family: 'Roboto', sans-serif;
        margin-left: auto;
        user-select: none;
        transition: 1s;
    }

    .main-container-top{
        margin-top: -7lvh;
    }

    .greet-nav-wrapper {
        margin-top: 40lvh;
        width: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 1rem;
        transition: 1s;
    }

    .greeter-left,
    .greeter
    {   
        position:absolute;
        z-index: 10;
        transition: 1s;
    }

    .greeter-left{
        margin-left: -19rem;
    }

    .nav {
        opacity: 1;
        transition: 1s;
        z-index: 9;
        margin-right: -19rem;
    }

    .nav-hidden {
        transition: 1s;
        opacity: 0;
        visibility: collapse;
    }

    .content,
    .stack-slide {
        text-align: left;
        width:36rem;
        margin:auto;
    }

    .contact-slide {
        margin-top: 2rem;
    }

    @media(max-width: 600px){
        .main-container,
        .nav,
        .greet-nav-wrapper,
        .content,
        .stack-slide,
        .contact-slide {
            display: block;
            width: 90%;
        }

        .main-container-top{
            margin-top: -14lvh;
        }

        .greeter,
        .greeter-left {
            position: relative;
            margin:auto;
        }

        .content,
        .stack-slide,
        .contact-slide {
            margin-left: 0vh;
        }
    }

    .slide-bottom {
    animation: 1s slide-bottom;
    }

    @keyframes slide-top {
    from {
        margin-top: -2%;
        opacity: 0;
    }
    to {
        margin-top: 0%;
        opacity: 100%;
    }
    }

    .slide-top {
    animation: 1s slide-top;
    }

    @keyframes slide-bottom {
        from {
        margin-top: 0%;
        opacity: 100%;
    }
    to {
        margin-top: -2%;
        opacity: 0%;
    }
    }

    .slide-right {
    animation: 1s slide-right;
    }

    @keyframes slide-right {
    from {
        margin-left: -2%;
    }
    to {
        margin-left: 0%;
    }
    }

    .slide-left {
    animation: 1s slide-left;
    }

    @keyframes slide-left {
    from {
        margin-left: 0%;
    }
    to {
        margin-left: -2%;
    }
    }
</style>