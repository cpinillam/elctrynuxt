<template>
    <div class="testimonials-clean">
           <div class="container">
               <div class="intro">
                   <h2 class="text-center">{{$t("Testimonios.testimonios")}}</h2>
                   <p class="text-center">{{$t("Testimonios.Testimonios_text")}}<br><br></p>
               </div>
               <div class="row people">
                   <div class="col-md-6 col-lg-4 item">
                       <div class="box">
                           <p class="description">{{$t("Testimonios.Testimonio_cliente")}}</p>
                         
                       </div>
                       <div class="author"><img class="rounded-circle" src="@/assets/img/1.jpg">
                           <h5 class="name">{{$t("Testimonios.Testimonio_cliente_nombre")}}</h5>
                           <p class="title">{{$t("Testimonios.Testimonio_cliente_cargo")}}</p>
                       </div>
                   </div>
                   <div class="col-md-6 col-lg-4 item">
                       <div class="box">
                           <p class="description">{{$t("Testimonios.Testimonio_segundo_cliente")}}</p>
                       </div>
                       <div class="author"><img class="rounded-circle" src="@/assets/img/1.jpg">
                           <h5 class="name">{{$t("Testimonios.Testimonio_segundo_cliente_nombre")}}</h5>
                           <p class="title">{{$t("Testimonios.Testimonio_segundo_cliente_cargo")}}</p>
                       </div>
                   </div>
                  
               </div>
           </div>
       </div>
</template>

<style scoped>
    @import '../../../assets/css/Testimonials.css';
</style>