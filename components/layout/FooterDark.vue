<template>
    <div class="footer-dark">
        <footer>
            <div class="container">
                <div class="row">
                    <div class="col-sm-6 col-md-3 item">
                        <h3>{{$t("Componentes.Footer.Quienes_somos")}}</h3>
                        <ul>
                            <li><a :href="$t('Routes.somos')">{{$t("Componentes.Footer.Empresa")}}</a></li>
                            <li ><a :href="$t('Routes.delegaciones')">{{$t("Componentes.Footer.Delegaciones")}}</a></li>
                            <li><a :href="$t('Routes.clientes')">{{$t("Componentes.Footer.Clientes")}}</a></li>
                            <li><a :href="$t('Routes.trabaja_con_nosotros')">{{$t("Componentes.Footer.Trabaja_con_nosotros")}}</a></li>
                        </ul>
                    </div>
                    <div class="col-sm-6 col-md-3 item">
                        <h3>{{$t("Componentes.Footer.Servicios")}}</h3>
                        <ul>
                            <li> {{$t("Componentes.Footer.Gestion_energetica")}}</li>
                            <li> {{$t("Componentes.Footer.Estudios_tecnicos")}}</li>
                            <li> {{$t("Componentes.Footer.Monitorizacion")}}</li>
                            <li> {{$t("Componentes.Footer.Eficiencia_energética")}}</li>
                        </ul>
                    </div>
                    <div class="col-sm-6 col-md-3 item text">
                        <h3>{{$t("Componentes.Footer.Contacto")}}</h3>
                        <p class="mb-3" v-html="$t('Componentes.Footer.Direccion_Barcelona')"></p>
                        <p  v-html="$t('Componentes.Footer.Direccion_Madrid')"></p>
                    </div>
                    <div class="col-sm-6 col-md-3 text-center text-sm-center text-md-left item social">
                        <h3 class="pb-3">{{$t("Componentes.Footer.Siguenos")}}</h3>
                        <a target="blank" :href="$t('Componentes.Footer.Facebook_url')"><i class="icon ion-social-facebook"></i></a>
                        <a target="blank" :href="$t('Componentes.Footer.twitter_url')"><i class="icon ion-social-twitter"></i></a>
                        <a target="blank" :href="$t('Componentes.Footer.instagram_url')"><i class="icon ion-social-instagram"></i></a>
                        <a target="blank" :href="$t('Componentes.Footer.linkedin_url')"><i class="icon ion-social-linkedin"></i></a>
                        </div>
                </div>
                <p class="copyright">ElectryConsulting&nbsp; © 2020 - <a :href="$t('Routes.politica_de_privacidad')" target="blank"> {{$t("Componentes.legalPolicy.Politica_de_privacidad")}} </a>- <a :href="$t('Routes.politica_de_cookies')" target="blank"> {{$t("Componentes.legalPolicy.Politica_de_cookies")}} </a>- <a :href="$t('Routes.politica_de_redes')" target="blank">{{$t("Componentes.legalPolicy.Politica_de_redes")}}</a></p>
            </div>
        </footer>
    </div>
</template>

<script>
    export default {
        name: "FooterDark"
    }
</script>

<style scoped>
    @import '../../assets/css/Footer-Dark.css';
</style>