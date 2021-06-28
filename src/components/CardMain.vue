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
            src-name="image-header-desktop.jpg"
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
        }
    }
</script>

<style scoped>
    div#CardMain {
        width: 1000px;

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

    @media screen and (max-width: 1000px) {
        div#CardMain {
            margin: 50px 0;

            width: 446px;

            flex-direction: column-reverse;
        }

        section#section, article#article {
            height: 100%;
        }

        article#article {
            width: calc(100% - 130px);
        }


        h1#card-main-title {
            margin: 60px 0 20px;
        }

        h1#card-main-title, p#card-paragraph {
            text-align: center;
        }

        p#card-paragraph {
            margin: 20px 0;

            width: calc(100% - 20px)
        }

        div#cards-sticky {
            flex-direction: column;
        }
    }
</style>