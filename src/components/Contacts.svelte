<script>
    import gitIcon from "../lib/assets/icons/git.png"
    import tgIcon from "../lib/assets/icons/telegram.png"
    import mailIcon from "../lib/assets/icons/gmail.png"
</script>


<div class="contact-wrapper">
    <div class="contact-row">
        <img class="icon" src={gitIcon} alt="error" href="https://github.com/531st">
        <a class="link" href="https://github.com/531st">github.com/531st</a>
    </div>
    <div class="contact-row">
        <img class="icon" src={tgIcon} alt="error" href="https://t.me/ElDespicable">
        <a class="link" href="https://t.me/ElDespicable">@ElDespicable</a>
    </div>
    <div class="contact-row">
        <img class="icon" src={mailIcon} alt="error" href="mailto:sasface88@gmail.com">
        <a class="link" href="mailto:sasface88@gmail.com">sasface88@gmail.com</a>
    </div>
</div>

<style>
    .contact-wrapper{
        display: flex;
        flex-direction: column;
        margin:auto;
        gap: 15px;
    }
    .contact-row{
        display: flex;
        flex-direction: row;
        gap: 1rem;
        flex-wrap: wrap;
        align-items: center;
    }

    .link{
        text-decoration: none;
        color: rgb(227, 227, 227);
    }

    .icon{
        height: 3rem;
        
    }
</style>