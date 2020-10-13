<template>
    <div class="col-12 mb-5 blog-card-item-slide">
        <a :href="'/blog/' + slug" >
        <div class="blog-items squared-blog round-card">
            <img :src=image>
            <h5>{{title}}<br></h5>
            
        </div>
        </a>
    </div>
</template>
<script>
export default {
    name: "blogCardSlide",
    props: {
        title: String,
        paragraph: String,
        date: String,
        slug: String,
        image: String

    }
    
}
</script>

<style  scoped>

</style>>
