<template>
    <div class="main-page">
        <div class="title">by catsolike</div>
        <div class="description">
            <p class="description__intro">Привет. Я catsolike, начинающий web-разработчик.</p>
            <cut-corners-wrapper class="list_wrapper">
                <p class="list__title">Изучаю технологии: </p>
                <ul class="list__techs">
                    <my-li class="list__item">Vue 3</my-li>
                    <my-li class="list__item">TypeScript</my-li>
                    <my-li class="list__item">SCSS</my-li>
                </ul>
            </cut-corners-wrapper>
            <p class="description__main">На этой странице представлены ссылки на публичные проекты, в разработке которых я участвовал</p>
        </div>

        <!-- <cut-corners-wrapper class="avatar">
            <img src="https://github.com/catsolike.png" alt="Avatar.jpg">
        </cut-corners-wrapper> -->

        <div class="links">
            <ul class="list__links">
                <li class="list__item">
                    <a href="https://catsolike.github.io/MathBattleship/">Math Battleship</a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {
name: 'main-page',
}
</script>

<style lang="scss" scoped>
//#region Variables
$title__font-size: 5.5rem;
$description__font-size: 2rem;
$techs__font-size: 3rem;
$links__font-size: 2.5rem;

//#endregion Variables
.main-page {
    display: grid;
    grid-template-columns: 1fr 40vw;
    grid-template-rows: $title__font-size 1fr 30vh;
    column-gap: 5rem;
    
    padding: 5vh 10vw;
    min-height: 100vh;
    min-width: 100vw;

    background: $page__bg;
}
.title {
    grid-column: 1 / 3;

    font-weight: bold;
    font-size: $title__font-size;
    letter-spacing: 0.4rem;
}
.description {
    grid-column: 1;

    overflow: auto;
    font-size: $description__font-size;

    &__intro {
        padding: 2rem 1rem;
    }
    
    &__main {
        padding: 2rem 1rem;
    }
}
.list {
    &_wrapper {
        width: 100%;
        padding: 0.5em 1.5em;
    }

    &__title {
        padding: 1rem;
    }
    
    &__techs {
        font-size: $techs__font-size;
        font-weight: bold;
        padding: 0 0 1rem 0;
    }
    
    &__links {
        font-weight: bold;
        font-size: $links__font-size;
    }

    &__item {
        // padding: 0 3rem;
    }
}

.avatar {
    grid-column: 1;
    grid-row: 3;
    width: max-content;
    height: max-content;
}

.links {
    grid-column: 2;
    grid-row: 2 / 4;

    max-height: 80vh;
    overflow: auto;
}

</style>