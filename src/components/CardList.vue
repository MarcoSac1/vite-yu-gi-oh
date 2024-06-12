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
    <section class="container">
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
        <h1>lunghezza {{ cards.length }}</h1>
    </section>
</template>

<style scoped>

</style>
