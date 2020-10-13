<template>
    <div class="blog-slider">
        <div class="blog-slider__wrp swiper-wrapper">
            <div class="blog-slider__item swiper-slide">
                <div></div>
                <div class="blog-slider__img"><img src="../../assets/img/blog-1.jpg"></div>
                <div class="blog-slider__content"><span class="blog-slider__code">26 December 2019</span><div class="blog-slider__title">Lorem Ipsum Dolor</div><div class="blog-slider__text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Recusandae voluptate repellendus magni illo ea animi? </div><a class="class=&quot;blog-slider__button" href="#">READ MORE</a></div>
            </div>
            <div class="blog-slider__item swiper-slide">
                <div></div>
                <div class="blog-slider__img"><img src="../../assets/img/blog-2.webp"></div>
                <div class="blog-slider__content"><span class="blog-slider__code">26 December 2019</span><div class="blog-slider__title">Lorem Ipsum Dolor</div><div class="blog-slider__text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Recusandae voluptate repellendus magni illo ea animi? </div><a class="class=&quot;blog-slider__button" href="#">READ MORE</a></div>
            </div>
            <div class="blog-slider__item swiper-slide">
                <div></div>
                <div class="blog-slider__img"><img src="../../assets/img/blog-3.webp"></div>
                <div class="blog-slider__content"><span class="blog-slider__code">26 December 2019</span><div class="blog-slider__title">Lorem Ipsum Dolor</div><div class="blog-slider__text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Recusandae voluptate repellendus magni illo ea animi? </div><a class="class=&quot;blog-slider__button" href="#">READ MORE</a></div>
            </div>
            <div class="blog-slider__pagination"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "SwiperBlog",
        created() {
            import('../../assets/js/swiper-slide.js')
        }
    }
</script>

<style scoped>

</style>