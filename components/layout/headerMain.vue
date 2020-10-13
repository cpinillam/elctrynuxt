<template>
    <div class="layout-simple">
       <nav class="navbar navbar-light navbar-expand-lg bg-white align-items-xl-center fixed-top" v-bind:class="[state ? open : close]">
            <div class="container">
                
                <a class="navbar-brand" href="/">
                    <img class="img-fluid" src="../../assets/img/logo-electryconsulting.svg">
                </a>

                <button data-toggle="collapse" class="navbar-toggler" data-target="#navcol-1" @click=toggle>
                   <span class="sr-only">Toggle navigation</span>
                   <img v-bind:src="[state ? imgclose : imgopen]"> 
                </button>

                <div class="collapse navbar-collapse flex-column align-items-end" id="navcol-1">
                    <div class="d-flex justify-content-end align-items-end navbar-top mr-3 top-header-link"> {{$t("Header_Main.Acceso")}} :<a target="blank" :href="$t('Routes.site_electryconsulting_com')" class="enlace-electry ml-1" rel="nofollow" >{{$t("Header_Main.Agentes")}}</a><a target="blank" :href="$t('Routes.site_electryconsulting_com')" class="enlace-electry ml-1" rel="nofollow"> / {{$t("Header_Main.Colaboradores")}}</a></div>
                    <ul class="nav navbar-nav text-uppercase">
                        <li class="nav-item dropdown"><a class="dropdown-toggle nav-link text-right text-lg-center" data-toggle="dropdown" aria-expanded="false" href="#"><strong>{{$t("Header_Main.Quienes_somos")}}</strong><br></a>
                            <div class="dropdown-menu dropdown-menu-right" role="menu">
                                <a class="dropdown-item text-right text-lg-center" role="presentation" :href="$t('Routes.somos')">{{$t("Header_Main.La_empresa")}}</a>
                                <a class="dropdown-item text-right text-lg-center" role="presentation" :href="$t('Routes.delegaciones')">{{$t("Header_Main.delegaciones")}}</a>
                            </div>
                        </li>
                        <li class="nav-item" role="presentation"><a class="nav-link text-right text-lg-center" :href="$t('Routes.servicios')"><strong>{{$t("Header_Main.Servicios")}}</strong><br></a></li>
                        <li class="nav-item" role="presentation"><a class="nav-link text-right text-lg-center" :href="$t('Routes.clientes')"><strong>{{$t("Header_Main.Nuestros_clientes")}}</strong><br></a></li>
                        <li class="nav-item" role="presentation"><a class="nav-link text-right text-lg-center" :href="$t('Routes.blog')"><strong>{{$t("Header_Main.Blog")}}</strong></a></li>
                        <li class="nav-item" role="presentation"><a class="nav-link text-right text-lg-center" :href="$t('Routes.contacto')"><strong>{{$t("Header_Main.Contacto")}}</strong></a></li>
                        <li class="nav-item " role="presentation"><a :href="$t('Routes.trabaja_con_nosotros')" class="btn btn-primary btn-sm shadow float-right float-lg-none mb-5 mt-3 mb-lg-0 mt-lg-0" style="transform:translateY(-3px);">{{$t("Home.Trabaja_con_nosotros")}}</a></li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>

import toggleClose from '@/assets/img/images/toggle-close.svg'
import toggleOpen from '@/assets/img/images/toggle.svg'


    export default {
        name: "HeaderMain",
        data(){
            return {
                state:false,
                open: 'mobile-custom-open',
                close: 'mobile-custom',
                imgclose: toggleClose,
                imgopen: toggleOpen,
            }
        },
        methods: {
            toggle(){
                this.state = !this.state;
                
            }
        }

        
    }
</script>

<style>
    @import '../../assets/css/header/header.compiled.css';
   
</style>

