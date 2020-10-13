<template>
    <div class="social-buttons">
        <a target="_blank" :data-href=currentUrl :href="'https://www.facebook.com/sharer/sharer.php?u='+ currentUrl + ';src=sdkpreparse'" class="social-buttons__button social-button social-button--facebook" aria-label="Facebook">
            <span class="social-button__inner">
            <i class="fab fa-facebook-f"></i>
            </span>
        </a>
       
        <a target="blank" :href="'https://www.linkedin.com/shareArticle?mini=true&url='+ currentUrl " class="social-buttons__button social-button social-button--linkedin" aria-label="LinkedIn">
            <span class="social-button__inner">
            <i class="fab fa-linkedin-in"></i>
            </span>
        </a>

        <a  href="https://twitter.com/intent/tweet" data-size="large" :data-url=currentUrl class="social-buttons__button social-button social-button--twitter" aria-label="twitter">
            <span class="social-button__inner">
            <i class="fab fa-twitter"></i>
            </span>
        </a>

        
        
    </div>
</template>

<script>
export default {
    name: "socialButtons",
    data(){
        return{
            currentUrl:"",
        }
    },
    created: function (){
        this.getCurrentUrl();
    },

    methods: {
        getCurrentUrl (){
            this.currentUrl = document.URL;

        }
    }

}
</script>

<style lang="sass" scoped>
    @import '@/assets/css/social-buttons.scss';   
</style>