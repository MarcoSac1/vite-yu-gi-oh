<script>

export default{
    components: {
        
    },
    data(){
        return{
            
        }
    },
    props:{
        archetypes:{
            type: Array,
            required: true
        }
    }
    
}
</script>

<template >
    <section class="container">
        <div class="dropdown ">
            <button class="btn btn-danger m-4  dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                Archetypes selector
            </button>
            <ul class="dropdown-menu dropdown-menu-dark">
                <li><a class="dropdown-item active" v-for="(archetypes, index) in archetypes" :key="index" :archetypes="archetypes" href="#">{{ archetypes.archetype_name }}</a></li>
            </ul>
        </div>
    </section>
</template>

<style scoped>

</style>
