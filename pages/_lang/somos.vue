<template>
    <div>
        <div class="block-titel no-radius">
            <div class="d-flex justify-content-between container">
                <div class="pl-4 pl-sm-2 pl-md-0">
                    <h1>{{$t("Somos.La_empresa")}}</h1>
                    <p>{{$t("Somos.Quienes_somos")}}</p>
                </div>
                <div class="d-none d-md-inline puntos"></div>
            </div>
        </div>
        <section class="d-flex flex-column align-items-center footer-radius" id="somos">
            <div class="container">
                <div class="row d-flex justify-content-between">
                    <div class="col-12 col-sm-11 col-md-6 col-lg-6 order-1 photo-square">

                       <div data-aos="fade-down" data-aos-duration="700" class="photo-center">
                           <img src="@/assets/img/ElectryConsulting-oficina.jpg" style="width: 140%;">
                        </div>
                        <img class="grafismo" src="@/assets/img/elctry-graf.svg">
                    </div>

                    <div class="col-12 col-sm-11 col-md-6 col-lg-7 order-1 mb-5 pt-5 pl-3 pr-4 px-md-5 py-md-1 px-5 justify-paragraph">
                        <p class="ofrecemos-content" style="width: 85%;" v-html="$t('Somos.text_quienes_somos')">
                            
                        </p>
                    </div>
                </div>
            </div>
        </section>
        <section class="d-flex flex-column align-items-center" id="mision">
            <div class="puntos-left"></div>
            <div class="container">
                <div class="row d-flex justify-content-between">
                    <div class="col-12 col-sm-11 col-md-6 col-lg-4 offset-0 offset-lg-1 offset-xl-0 order-1 px-md-1 px-5 justify-paragraph">
                        <h1 class="mb-4">{{$t("Somos.Mision")}}</h1>
                        
                        <p class="ofrecemos-content" v-html="$t('Somos.text_mision')">
                        </p>
                    </div>
                    <div class="col-12 col-sm-11 col-md-6 col-lg-7 order-1 mb-5 pt-5 pl-3 pr-4 px-md-5 py-md-1">

                            <div data-aos="fade-down" data-aos-duration="700" class="photo-square">
                                <div class="photo-center"><img src="@/assets/img/work-us-color.jpg" style="width: 153%;"><img class="grafismo" src="@/assets/img/elctry-graf.svg"></div>
                            </div>

                    </div>
                </div>
            </div>
        </section>
        <section class="d-flex flex-column align-items-center justify-paragraph" id="vision">
            <div class="container">
                <div class="row d-flex justify-content-between">
                    <div class="col-12 col-sm-11 col-md-6 col-lg-6 order-2 order-md-1 photo-square" data-aos="fade-right" data-aos-duration="750">
                        <div class="photo-center"><img src="@/assets/img/vision-empresa.jpg" style="width: 120%;"></div><img class="grafismo" src="@/assets/img/elctry-graf.svg"></div>
                    <div class="col-12 col-sm-11 col-md-6 col-lg-7 order-1 order-md-2 mb-5 pt-5 pl-3 pr-4 px-md-5 py-md-1 px-5 padding-somos">
                        <h1 class="mb-4">{{$t("Somos.Vision")}}</h1>
                        <p class="ofrecemos-content" style="width: 90%;" v-html="$t('Somos.text_vision')">
                           </p>
                    </div>
                </div>
            </div>
        </section>
        <section class="d-flex flex-column align-items-center border-radius-top justify-paragraph" id="valores">
            <div class="puntos-rigth"></div>
            <div class="container">
                <div class="row d-flex justify-content-between">
                    <div class="col-12 col-sm-11 col-md-6 col-lg-5 order-1">
                        <div style="background-color: #ffffff;padding: 50px;border-radius: 50px;">
                            <h1 class="mb-4">{{$t("Somos.Valores")}}</h1>
                            <p class="ofrecemos-content" v-html="$t('Somos.text_valores')">
                             </p>
                        </div>
                    </div>
                    <div class="col-12 col-sm-11 col-md-6 col-lg-7 order-1 mb-5 pt-5 pl-3 pr-4 px-md-5 py-md-1 px-5">
                        <div data-aos="fade-up" class="photo-square">
                            <div class="photo-center"><img src="@/assets/img/valores-empresa.jpg" style="width: 160%;"><img class="grafismo" src="@/assets/img/elctry-graf.svg"></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <div class="newsletter-subscribe">
            <div class="container">
                <div class="text-center intro">
                    <h2 class="text-center mt-4">{{$t("Componentes.Cta_Ofertas.Ofertas_text")}}<br><br></h2>
                    <a href="jobs" class="enlace-electry btn-cristal-blue mb-5">{{$t("Componentes.Cta_Ofertas.Ofertas_Boton_text")}}</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Somos",    
    }
</script>
