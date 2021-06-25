<template>
    <div id="CardMain">
        <article id="article" role="article">
            <h1 id="title-card-main">
                Get <span id="strong-word">insights</span> that help your business grow.
            </h1>
        </article>
        <CardImage
            src-name="image-header-desktop.jpg"
            alt-name="Image de fundo"
            background-color="hsl(277, 64%, 61%)"
        />
    </div>
</template>

<script>
    import CardImage from './CardImage.vue';

    export default {
        name: 'CardMain',
        components: {
            CardImage,
        },
    }
</script>

<style scoped>
    div#CardMain {
        width: calc(100% - 300px);

        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

        border-radius: 10px;

        display: flex;
        justify-content: space-between;
        align-items: center;

        background-color: var(--dark-desaturated-blue);
    }

    h1#title-card-main {
        font-family: 'Lexend Deca';
        
        color: var(--white);

        font-size: 40px;

        text-align: left;
    }

    span#strong-word {
        color: var(--soft-violet)
    }

    article#article {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;

        width: 100%;
    }
</style>