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
                <li v-for="(archetypes, index) in archetypes" :key="index" :archetypes="archetypes">
                    <a class="dropdown-item active"  href="#">{{ archetypes.archetype_name }}</a>
                </li>
            </ul>
        </div>
    </section>
</template>

<style scoped>

</style>
