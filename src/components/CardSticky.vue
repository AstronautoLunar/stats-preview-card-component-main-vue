<template>
    <div class="CardSticky">
        <span class="value">
            {{ value }}
        </span>
        <span class="type">
            {{ type }}
        </span>
    </div>
</template>

<script>
    export default {
        name: "CardSticky",
        components: {

        },
        props: {
            value: {
                type: String,
                required: true,
            },
            type: {
                type: String,
                required: true,
            },
        }
    }
</script>

<style scoped>
    div.CardSticky {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: flex-start;

        height: 60px;
    }

    span.value {
        color: var(--white);

        font-size: 30px;

        font-weight: 700
    }

    span.value, span.type {
        font-family: Inter;
    }

    span.type {
        color: var(--slightly-transparent-white-stat-headings);
    }

    @media screen and (max-width: 1000px) {
        div.CardSticky {
            align-items: center;

            margin: 20px 0;
        }
    }

    @media screen and (max-width: 472px) {
        div.CardSticky:last-of-type {
            margin-bottom: 40px;
        }   
    }
</style>