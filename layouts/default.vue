<template>
  <div>
     <header-main></header-main>
    <div style="min-height:60vh;">
     <Nuxt />
    </div>
    <footer-dark></footer-dark>
    
  </div>
</template>


<script>

  import HeaderMain from "../components/layout/headerMain";
  import FooterDark from "../components/layout/FooterDark";

  
  export default {
    components: {HeaderMain, FooterDark},
    head:{
      title: 'Consultoría energética - ElectryConsulting',      
    meta: [
      { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' },
      { hid: 'description', name: 'description', content: 'ElectryConsulting es una consultoría energética que ofrece soluciones integrales para reducir el importe de las facturas de luz y gas.' },
      { property: 'og:title', content: "Consultoría energética - ElectryConsulting"},
      { property: 'og:site_name', content: 'ElectryConsulting - Consultoría energética'},
      { property: 'og:type', content: 'website'},
      { property: 'og:description', content: 'Empresa consultora de energía, gestionamos su factura de energía y la optimizamos para ofrecerle el mejor ahorro en los costes energéticos.'},
      { property: 'og:image', content: 'https://electryconsulting.com/img/logo.png'},
     
      { name: 'robots', content: 'index,follow'}, 
      { name: 'googlebot', content: 'index,follow,max-snippet:-1,max-image-preview:large,max-video-preview:-1'}, 
      { name: 'bingbot', content: 'index,follow,max-snippet:-1,max-image-preview:large,max-video-preview:-1'} 
    ],
    }
  
  }

</script>

