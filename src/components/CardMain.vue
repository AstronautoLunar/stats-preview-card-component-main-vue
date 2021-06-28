<template>
    <div id="CardMain">
        <section id="section" role="section">
            <article id="article" role="article">
                <h1 id="card-main-title">
                    Get <span id="strong-word">insights</span> that help your business grow.
                </h1>
                <p id="card-paragraph">
                    Discover the benefits of data analytics and make better decisions regarding revenue, customer experience, and overall efficiency.
                </p>
                <div id="cards-sticky">
                    <CardSticky
                        v-for="item in cardsStickys"
                        :key="item.id"
                        :type="item.type"
                        :value="item.value"
                    />
                </div>
            </article>
        </section>
        <CardImage
            :src-name="currentImage"
            alt-name="Image de fundo"
            background-color="hsl(277, 64%, 61%)"
        />
    </div>
</template>

<script>
    import CardSticky from './CardSticky.vue';
    import CardImage from './CardImage.vue';

    export default {
        name: 'CardMain',
        components: {
            CardImage,
            CardSticky,
        },
        data() {
            return {
                cardsStickys: [],
                currentImage: "",
            }
        },
        created() {
            this.cardsStickys = [
                {
                    id: 1,
                    value: "10k+",
                    type: "COMPANIES",
                },
                {
                    id: 2,
                    value: "314",
                    type: "TEMPLATES",
                },
                {
                    id: 3,
                    value: "12M+",
                    type: "QUERIES",
                },
            ]


            const mediaQuerieList = matchMedia('(max-width: 1350px)')

            let currentImageRender = "";

            function componentRender(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    currentImageRender = "image-header-mobile.jpg";

                    console.log("Mobile")
                } else {
                    currentImageRender = "image-header-desktop.jpg";

                    console.log("Desktop")
                }
            }

            componentRender(mediaQuerieList);
            this.currentImage = currentImageRender;
            mediaQuerieList.addEventListener('change', componentRender);

        }
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

    section#section {
        display: flex;
        justify-content: center;
        align-items: center;
        
        width: 100%;
        height: 446px;
    }

    article#article {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;

        width: 400px;
        height: 346px;
    }

    h1#card-main-title, p#card-paragraph {
        font-family: 'Lexend Deca';
        
        margin-bottom: 0;
        margin-top: 0;
    }

    h1#card-main-title {
        
        color: var(--white);

        font-size: 35px;

        text-align: left;


    }

    span#strong-word {
        color: var(--soft-violet)
    }

    p#card-paragraph {
        color: var(--slightly-transparent-white-main-paragraph);

        line-height: 28px;

        margin-bottom: 35px;
    }

    div#cards-sticky {
        display: flex;
        justify-content: space-between;
        align-items: center;

        width: 100%;
    }

    @media screen and (max-width: 1350px) {
        div#CardMain {
            width: 645px;
        }
    }
</style>