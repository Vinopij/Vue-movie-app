<template>
    <header class="header">
        <div class="logo">
            <a href="https://www.themoviedb.org/" target="blank">
                <img alt="The Movie Database (TMDB)" className="logoPage" src="https://files.readme.io/29c6fee-blue_short.svg">
            </a>
        </div>
        <div className="text-header">
            Witaj piękny <span> koniu! </span>
        </div>
    </header>
</template>

<script>

</script>

<style scoped>

    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 15px;
        background-color: lightgray;
        opacity: 0.8;
        padding: 25px;
        height: 100px;
    }
    .logo {
        width: 35%;
        padding: 30px;
    }
    .logo:hover {
        cursor: pointer;
    }
    .text-header {
        font-size: 25px;
        font-weight: bold;
        font-style: italic;
        padding: 70px;
    }
    .text-header span {
        color: purple;
        font-size: 40px;
        text-transform: uppercase;
    }

</style>