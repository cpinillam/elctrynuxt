<template>
    <div class="col-12 col-sm-6 col-lg-4 mb-3 blog-card-item">
        <a :href="'/blog/' + slug" >
        <div class="blog-items squared-blog round-card">
            <img :src=image>
            <h5>{{title}}<br></h5>
            <p v-html="paragraph"></p>
            <p>{{date}}</p>
        </div>
        </a>
    </div>
</template>
<script>
export default {
    name: "blogCard",
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
    @import '../../assets/css/jobs.css';
</style>>
