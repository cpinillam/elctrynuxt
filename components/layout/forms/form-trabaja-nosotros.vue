<template>
    <div>
        <loader :successLoader=success :errorLoader=error :loadingLoader=loading ></loader>
         <fieldset :disabled="loading">
        <form method="post" @submit.prevent="enviarMsg" class="mb-5">
            <div class="form-group"><input class="form-control" required type="text" id="ctaName" v-model="ctaName" name="nombre" :placeholder="$t('Componentes.InputsPlaceholder.Nombre')"></div>
            <div class="form-group"><input class="form-control" required type="tel" id="ctaEmail" v-model="ctaEmail" name="email" :placeholder="$t('Componentes.InputsPlaceholder.Email')"></div>
            <div class="form-group"><input class="form-control" required type="tel" id="ctaPhone" v-model="ctaPhone" name="telefono" :placeholder="$t('Componentes.InputsPlaceholder.Telefono')"></div>
            <div class="form-group"><input class="form-control" required type="text" id="ctaCiudad" v-model="ctaCiudad" name="ciudad" :placeholder="$t('Componentes.InputsPlaceholder.Ciudad')"></div>
            <div class="form-group"><input class="form-control" required type="text" id="ctaPuesto" v-model="ctaPuesto" name="puesto" :placeholder="$t('Componentes.InputsPlaceholder.ultimo_puesto')"></div>
            <div class="form-group selectRadio">
                <h2 class="text-center" >¿Tienes experiencia en el sector energético?</h2>
                <label> <input  type="radio" name="experiencia" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaExperiencia"> {{$t("Jobs.si")}}</label>
                <label> <input  type="radio" name="experiencia" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaExperiencia"> {{$t("Jobs.no")}}</label>
            </div>

            <div class="form-group selectRadio">
                <h2 class="text-center" >¿Tienes cartera propia?</h2>
                <label> <input  type="radio" name="cartera" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaCartera"> {{$t("Jobs.si")}}</label>
                <label> <input  type="radio" name="cartera" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaCartera"> {{$t("Jobs.no")}}</label>
            </div>

            <div class="form-group selectRadio">
                <h2 class="text-center" >¿Tienes experiencia en la gestión de equipos?</h2>
                <label> <input  type="radio" name="gestionequipos" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaGestion"> {{$t("Jobs.si")}}</label>
                <label> <input  type="radio" name="gestionequipos" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaGestion"> {{$t("Jobs.no")}}</label>
            </div>
            
             <input type="submit" :value="$t('Componentes.InputsPlaceholder.Te_llamamos')" class="btn-cristal-blue mb-2">
             <legalTextPolicyJobs></legalTextPolicyJobs>
             <legalTextAdvertisingJobs></legalTextAdvertisingJobs>
        </form>
         </fieldset>
    </div>
</template>

<script>

import loader from "../../../components/layout/loader";
import legalTextPolicyJobs from "../../../components/layout/forms/legalTexts/legal-text-policy-jobs";
import legalTextAdvertisingJobs from "../../../components/layout/forms/legalTexts/legal-text-advertising-jobs";

export default {
        name: "FormTrabajaNosotros",
        components: {
            loader,
            legalTextPolicyJobs,
            legalTextAdvertisingJobs
        },
        data(){
            return {
                ctaName: "",
                ctaEmail: "",
                ctaPhone: "",
                ctaPuesto: "",
                ctaCiudad: "",
                ctaExperiencia: "",
                ctaGestion: "",
                ctaCartera: "",
                ctaCheck: "",

                success: false,
                error: false,
                loading: false
   
            }
        },
        methods: {
            validaMsg(){
                if (this.ctaName && this.ctaPhone && this.ctaPuesto && this.ctaCheck){
                    this.enviarMsg();    
                }
                else {
                   alert("faltan completar campos"); 
                }

            },    

            enviarMsg(){
                this.loading = true;

                let headers = {'Content-Type': 'multipart/form-data' };
                let bodyFormData = new FormData();
                    bodyFormData.append('nombre', this.ctaName);
                    bodyFormData.append('telefono', this.ctaPhone);
                    bodyFormData.append('email', this.ctaEmail);
                    bodyFormData.append('puesto', this.ctaPuesto);
                    bodyFormData.append('ciudad', this.ctaCiudad);
                    bodyFormData.append('experiencia', this.ctaExperiencia);
                    bodyFormData.append('cartera', this.ctaCartera);
                    bodyFormData.append('gestion', this.ctaGestion);

                this.axios.post("contact-form-7/v1/contact-forms/76/feedback", bodyFormData, {
                headers: headers
                        })
                .then((response)=> {
                         this.success = true;     
                         location.href="/trabaja-con-nosotros/gracias";                         
                         setTimeout(this.reset, 2000);


                }).catch((error) => {
                        this.error = true;
                        setTimeout(this.reset, 4000);
                        console.log(error);

                    }).finally(() => {
                        this.loading = false;
                        
                    });
            },

            reset(){
                this.success = false;
                this.error = false;
                this.ctaName = "";
                this.ctaPhone = "";
                this.ctaEmail = "";
                this.ctaPuesto = "";
                this.ctaCiudad = "";
                this.ctaExperiencia = "";
                this.ctaCartera = "";
                this.ctaGestion = "";
                this.ctaCheck = "";
            }
            
           

        }

    }
</script>

<style scoped>

    @import '../../../assets/css/jobs.css';


</style>