<template>
    <div 
        id="CardImage"
        :style="style"
    >
        <img
            id="image"
            :style="opacityImage"
            :src="require(`../assets/${srcName}`)"
            :alt="altName"
        />
    </div>
</template>

<script>

    export default {
        name: 'CardImage',
        components: {

        },
        props: {
            srcName: {
                type: String,
                required: true,
            },
            altName: {
                type: String,
                required: true,
            },
            backgroundColor: {
                type: String,
                required: true,
            },
        },
        data() {
            return {
                style: "",
                opacityImage: "",
            }
        },
        created() {
            this.style = `background-color: ${this.backgroundColor};`

            if(this.style !== `background-color: undefined;`) {
                this.opacityImage = "opacity: 0.8;"
            }
        }
        
    }
</script>

<style scoped>
    div#CardImage {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    img#image, div#CardImage {
        border-top-right-radius: 10px;
        border-bottom-right-radius: 10px;
    }

    @media screen and (max-width: 1000px) {
        div#CardImage > img#image {
            width: 100%;
        }

        img#image, div#CardImage {
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
        }
    }
</style>