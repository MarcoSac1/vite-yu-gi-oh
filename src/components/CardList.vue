<script>
import CardCaracters from './CardCaracters.vue'

export default{
    components:{
        CardCaracters
    },
    data(){
        return{

        }
    },
    props:{
        cards:{
            type: Array,
            required: true
        }
    }
}
</script>

<template>
    <CardCaracters/>
    <section class="container p-5 mb-4">
        <h1 class=" text-light"> Generated cards: {{ cards.length }}</h1>
        <div class="col-12">
            <div class="row">
                <article v-for="(cards, index) in cards" :key="index" class="col-3 p-2">
                    <div class="card w-100 h-100 p-2">
                        <img :src=" cards.card_images[0].image_url" class="card-img-top" alt="...">
                        <div class="card-body text-center">
                            <p class="card-text ">{{ cards.name }}</p>
                            <p class="card-text">{{ cards.archetype }}</p>
                        </div>
                    </div>
                </article>
            </div>
        </div>
    </section>
</template>

<style scoped>
section.container{
    background-image: linear-gradient( -90deg,  #e4e26d 5%, #ff4b4b 100%);
}
</style>
