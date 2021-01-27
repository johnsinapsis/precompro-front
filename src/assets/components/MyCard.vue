<template>
    <div class="card">
        <div class="card-image">
            <figure class="image is-4by3">
            <img :src="card.image" alt="Placeholder image">
            </figure>
        </div>
        <div class="card-content">
            <div class="media">
            <div class="media-left">
                <figure class="image is-48x48">
                <img :src="card.image" alt="Placeholder image">
                </figure>
            </div>
            <div class="media-content">
                <p class="title is-4">{{card.title}}</p>
            </div>
            </div>

            <div class="content">
                {{card.description}}
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:{
        card: Object
    }
}
</script>