<template>
    <b-carousel :arrow="arrow">
        <b-carousel-item v-for="(image, i) in carousel" :key="i">
            <section class="hero is-medium">
                <figure class="image is-16by9 hero-body has-text-centered">
                    <img  :src="image.src" :alt="image.name">
                </figure>
            </section>
        </b-carousel-item>
    </b-carousel>
</template>

<script>
export default {
    props:{
        carousel: Array
    },
    data(){
        return {
           arrow: false,
        }
    }
}
</script>
<style lang="scss">

</style>