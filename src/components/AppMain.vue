<script>
import CardList from './CardList.vue';
import axios from 'axios';
export default{
    components: {
        CardList
    },
    data(){
        return{
            cards:[],
        }
    },
    methods:{
        getCards(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response) => {
                console.log(response.data.data);
                this.cards=response.data.data;
            })
            .catch(function(error){
                console.log(error);
            })
            .finally(function () {
                
            });
        }
    },
    created(){
        this.getCards();
    }
}
</script>

<template>
    <main>
        <CardList :cards="cards"/>
    </main>
</template>

<style scoped>

</style>
