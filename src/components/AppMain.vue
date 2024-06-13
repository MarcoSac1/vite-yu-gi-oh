<script>
import AppSearch from './AppSearch.vue';
import CardList from './CardList.vue';
import axios from 'axios';
export default{
    components: {
        CardList,
        AppSearch
    },
    data(){
        return{
            cards:[],
            archetypes: []
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
        },
        getArchetypes(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
                console.log(response.data);
                this.archetypes=response.data;
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
        this.getArchetypes();
    }
}
</script>

<template>
    <main>
        <AppSearch :archetypes="archetypes"/>
        <CardList :cards="cards"/>
    </main>
</template>

<style scoped>

</style>
