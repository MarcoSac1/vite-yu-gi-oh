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
    <section>
        <h1>lunghezza {{ cards.length }}</h1>
    </section>
</template>

<style scoped>

</style>
