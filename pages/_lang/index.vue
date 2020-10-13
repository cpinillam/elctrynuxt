<template>

  <div class="home">
    <div class="hero">
      <div class="container-fluid hero-home turn-off-txt" id="hero-content">
        <div id="hero-footer-bg" class="color-main-blue"></div>
        <particlesBg></particlesBg>
        <div id="hero-main" class="hero-home-main">
          <div class="row d-flex align-items-start align-items-md-center hero-row">
            <div class="col-12 col-md-5 d-flex flex-column">
              <h1 class="text-left">{{$t("Home.header_home")}}</h1>
              <a href="jobs" class=" btn  btn-cristal  white ml-3 ml-sm-1" id="btn-hero-cta">{{$t("Home.header_home_btn")}}</a>
            </div>
            <div class="col-12 col-md-5 offset-md-2 text-right d-none d-md-block hero-grafico"><a class="enlace-electry" href="delegaciones"><img class="img-fluid" id="graph-hero" src="@/assets/img/grafismo-delegaciones.png" loading="lazy"></a></div>
          </div>
        </div>
      </div>
      <div class="d-flex justify-content-center align-items-end bombilla" id="bulb-brillo-1">
        <div class="img-fluid bombilla-img" style="opacity: 0.3;filter: blur(91px);mix-blend-mode: color-burn;"><div style="height: 40vh; width: 50vw; background-color: rgb(243, 229, 169);"></div></div>

        </div>
     <bombillaMain></bombillaMain>
      <div class="d-flex justify-content-center align-items-end bombilla" id="bulb-brillo"></div>
    </div>

   
    <section class="d-flex flex-column align-items-center" id="que-ofrecemos">
      <h2 class="heading-section"><span>{{$t("Home.Servicios")}}</span></h2>
      <div class="row d-flex flex-column justify-content-center align-items-center flex-sm-row align-items-sm-start w-100 molino-footer">
        <div class="col-12 que-hacemos-footer">
          <div></div>
        </div>
        <div class="col-10 col-md-4 col-lg-4 col-xl-3 order-1">
          
          <nuxt-link class="enlace-electry" to="/">
            <div class="d-flex ofrecemos-item">
              <div class="ofrecemos-item-icon"><i class="fas fa-charging-station"></i></div>
              <div class="ofrecemos-item-text">
                <h4 class="mb-1 ofrecemos-title">{{$t("Home.Gestion_energetica")}}</h4>
                <p class="ofrecemos-content">{{$t("Home.Gestion_energetica_text")}}<br></p>
              </div>
            </div>
          </nuxt-link>

         
          <nuxt-link class="enlace-electry" to="/">
            
            <div class="d-flex ofrecemos-item">
              <div class="ofrecemos-item-icon"><i class="fab fa-searchengin"></i></div>
              <div class="ofrecemos-item-text">
                <h4 class="mb-1 ofrecemos-title">{{$t("Home.Estudios_tecnicos")}}<br></h4>
                <p class="ofrecemos-content">{{$t("Home.Estudios_tecnicos_text")}}<br></p>
              </div>
            </div>
          </nuxt-link>
         
        </div>
        <div class="col-10 col-sm-6 col-md-4 col-lg-4 col-xl-3 order-3 order-md-2 molino-svg">
        <MolinoHome></MolinoHome>
        </div>
        <div class="col-10 col-md-4 col-lg-4 col-xl-3 order-2">

          <nuxt-link class="enlace-electry" to="/">
            <div class="d-flex ofrecemos-item">
              <div class="text-left text-md-right order-2 order-md-1 ofrecemos-item-text">
                <h4 class="mb-1 ofrecemos-title">{{$t("Home.Monitorizacion")}}<br></h4>
                <p class="ofrecemos-content">{{$t("Home.Monitorizacion_text")}}<br></p>
              </div>
              <div class="text-left text-md-right order-1 order-md-2 ofrecemos-item-icon"><i class="fas fa-satellite-dish"></i></div>
            </div>
          </nuxt-link>

            <nuxt-link class="enlace-electry" to="/">
            <div class="d-flex ofrecemos-item">
              <div class="text-left text-md-right order-2 order-md-1 ofrecemos-item-text">
                <h4 class="mb-1 ofrecemos-title">{{$t("Home.Eficiencia_energetica")}}<br></h4>
                <p class="ofrecemos-content">{{$t("Home.Eficiencia_energetica_text")}}<br></p>
              </div>
              <div class="text-left text-md-right order-1 order-md-2 ofrecemos-item-icon"><i class="fas fa-solar-panel"></i></div>
            </div>         
            </nuxt-link>

        </div>
        <div class="col-12 order-4 padding-footer">
          <div></div>
        </div>
      </div>
    </section>


    
    <div class="newsletter-subscribe pt-5 pb-5">
      <div class="container">
        <div class="text-center intro">
          <h2 class="text-center">{{$t("Home.Ya_puedes_pagar_menos")}}<br></h2>
        </div>
        <form-cta-phone></form-cta-phone>
      </div>
    </div>
    

    <section class="d-flex flex-column align-items-center" id="nos-diferencia">
      <div class="col-2 col-sm-2 col-md-1 secction-symbol"><img class="symbol-section" src="@/assets/img/simbol.svg"></div>
      <div class="row d-flex flex-column justify-content-center align-items-start flex-sm-row align-items-sm-start w-100 molino-footer">
        <div class="col-12 col-md-4 text-left text-md-right order-2 px-5 px-md-3">
          <div class="d-flex flex-column ">
            <h4 class="mb-1 ofrecemos-title">{{$t("Home.Asesoría_100")}}</h4>
            <p class="ofrecemos-content">{{$t("Home.Siempre_tendrás_un_asesor")}}</p>
          </div>
          <div class="d-flex flex-column ">
            <h4 class="mb-1 ofrecemos-title">{{$t("Home.Lideres_en_optimizacion")}}</h4>
            <p class="ofrecemos-content">{{$t("Home.Con_mas_de_10")}}</p>
          </div>
          <div class="d-flex flex-column ">
            <h4 class="mb-1 ofrecemos-title">{{$t("Home.Formacion_continua")}}</h4>
            <p class="ofrecemos-content">{{$t("Home.Consideramos_que_la_formacion")}}</p>
          </div>
        </div>
        <div class="col-10 col-sm-6 col-md-3 align-self-center order-1 order-md-2">
          <h1 class="text-center mb-5">{{$t("Home.Lo_que_nos_diferencia")}}</h1>
        </div>
        <div class="col-12 col-md-4 order-3 px-5 px-md-3">
          <div class="d-flex flex-column ">
            <h4 class="mb-1 ofrecemos-title">{{$t("Home.Emprendimiento")}}</h4>
            <p class="ofrecemos-content" v-html="$t('Home.Contamos_con_una_incubadora')"></p>
          </div>
          <div class="d-flex flex-column ">
            <h4 class="mb-1 ofrecemos-title">{{$t("Home.Internacionalizacion")}}</h4>
            <p class="ofrecemos-content">{{$t("Home.Ademas_de_gestionar")}}</p>
          </div>
        </div>
      </div>
    </section>

    <logosCompanies></logosCompanies>

    <div class="d-flex flex-column justify-content-center align-items-center justify-content-xl-center align-items-xl-center work-us-parallax" data-bs-parallax-bg="true" >
      <h1 class="mx-4" style="color: rgb(255,255,255);font-size: 67px;">{{$t("Home.Trabaja_con_nosotros")}}</h1>
      <p class="mx-4" style="color: rgb(255,255,255);">{{$t("Home.unete_a_la_red")}}<br></p>
      <a href="trabaja-con-nosotros" class="enlace-electry btn-cristal-blue mb-5">{{$t("Home.Ofertas_disponibles")}}</a>
    </div>

    <h4 class="text-center text-white-50 pt-4 pb-4 mb-0" style="background-color: #282d32;font-weight: 100;">{{$t("Home.Nuestros_eventos")}}</h4>
   <FotosEventos></FotosEventos>


  </div>
</template>

<script>  

    import bombillaMain from "../../components/Home/bombillaMain.vue";
    import FotosEventos from "../../components/FotosEventos.vue";
    import FormCtaPhone from "../../components/layout/forms/form-cta-phone.vue";
    import MolinoHome from "../../components/Home/molino-home.vue";
    import particlesBg from "../../components/Home/particlesBg.vue";
    import logosCompanies from "../../components/layout/logosCompanies.vue";

export default {
  name: 'Home',
  components: {
      FormCtaPhone,
      MolinoHome, 
      FotosEventos,
      logosCompanies,
      particlesBg,
      bombillaMain
      
    },

    head: {
    title: 'Consultoría energética - ElectryConsulting',
    meta: [
      { hid: 'description', name: 'description', content: 'ElectryConsulting es una consultoría energética que ofrece soluciones integrales para reducir el importe de las facturas de luz y gas.' },
      { property: 'og:title', content: "Consultoría energética - ElectryConsulting"},
      { property: 'og:site_name', content: 'ElectryConsulting - Consultoría energética'}
    ],
    
  },
    created() {   
      import("../../assets/js/alertBy");
    }
   
}
</script>

<style>

  .work-us-parallax {
  height: 600px;
  background-image: url("../../assets/img/work-us.jpg");
  background-position: center;
  background-size: cover;

}

  
  .estart {
    color: blue;
    text-decoration: underline;
    }

  .estart:hover {
      color: rgb(0, 162, 255);  
  }

 
  
</style>

