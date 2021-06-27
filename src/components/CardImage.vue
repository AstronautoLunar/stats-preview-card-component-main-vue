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
    //require(`../assets/${srcName}`)

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
</style>