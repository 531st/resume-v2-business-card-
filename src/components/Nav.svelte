<script>
    export let position='';
    export let show=false;

    function handleClick(pos){
        position=pos;
        show = true;
    }
</script>


<div class="nav-row">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    <p on:click={()=>{handleClick('about')}}>about</p>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    <p on:click={()=>{handleClick('specs')}}>specs</p>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    <p on:click={()=>{handleClick('stack')}}>stack</p>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    <p on:click={()=>{handleClick('contacts')}}>contacts</p>
</div>

<style>
    .nav-row {
        display: flex;
        flex-direction: row;
        gap: 10px;
    }

    p {
        color:rgb(227, 227, 227);
        font-size: 1.4rem;
        transition-duration: 200ms;
    }

    p:hover{
        transform: translateY(-5px);
    }
</style>