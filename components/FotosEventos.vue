<template>
   <div class="photo-gallery">
       <CoolLightBox
               :items="items"
               :index="index"
               loop
               @close="index = null">
       </CoolLightBox>


      <div class="row photos mx-0">

        <div class="col-4 col-sm-4 col-md-3 col-lg-2 item" v-for="(image, imageIndex) in items" :key="imageIndex"  @click="index = imageIndex">
             <div class="squared"><img class="img-fluid" :src="image.src"  loading="lazy"></div>
        </div>

      </div>
    </div>


</template>


<script>
import CoolLightBox from 'vue-cool-lightbox'

import fotoEvento2 from '../assets/img/eventos/eventos_2.jpg'
import fotoEvento3 from '../assets/img/eventos/eventos_3.jpg'
import fotoEvento4 from '../assets/img/eventos/eventos_4.jpg'
import fotoEvento5 from '../assets/img/eventos/eventos_5.jpg'
import fotoEvento6 from '../assets/img/eventos/eventos_6.jpg'
import fotoEvento7 from '../assets/img/eventos/eventos_7.jpg'
import fotoEvento8 from '../assets/img/eventos/eventos_8.jpg'
import fotoEvento9 from '../assets/img/eventos/eventos_9.jpg'
import fotoEvento10 from '../assets/img/eventos/eventos_10.jpg'
import fotoEvento12 from '../assets/img/eventos/eventos_12.jpg'
import fotoEvento13 from '../assets/img/eventos/eventos_13.jpg'
import fotoEvento14 from '../assets/img/eventos/eventos_14.jpg'

export default {
    name: "FotosEventos",
    data: function () {
            return {
            items:
                [
                   
                    {
                        src: fotoEvento2,
                    },
                    {
                        src: fotoEvento3,
                    },
                    {
                        src: fotoEvento4,
                    },
                    {
                        src: fotoEvento5,
                    },
                    {
                        src: fotoEvento6,
                    },
                    {
                        src: fotoEvento7,
                    },
                    {
                        src: fotoEvento8,
                    },
                    {
                        src: fotoEvento9,
                    },
                    {
                        src: fotoEvento10,
                    },
                   
                    {
                        src: fotoEvento12,
                    },
                     {
                        src: fotoEvento13,
                    },
                     {
                        src: fotoEvento14,
                    },
                ],
                index: null
            };
            },
    components: {
        CoolLightBox
    },
    methods: {
        setIndex(index) {
            this.index = index
        }
    }
};

</script>

<style scoped>
@import '../assets/css/Lightbox-Gallery.css';
</style>