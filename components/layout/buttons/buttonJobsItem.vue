<template>
    <div class="col-12 col-sm-6 col-md-6 col-lg-4 col-xl-3 mb-4 job-item-card">
       
        <a :href="'/oferta-empleo/' + linkJob" >
        <div class="squared squared-blog round-card">
            <h5>{{titulo}}<br></h5>
            <p>{{UbicationJob}}</p>
        </div>
        </a>
    </div>
</template>
<script>
export default {
    name: "buttonJobsItem",
    data (){
        return {
            titulo : this.titleJob.slice(0,54),
        }
    },
    props: {
        titleJob: String,
        UbicationJob: String,
        linkJob: String
    }
    
}
</script>

<style  scoped>

</style>>
