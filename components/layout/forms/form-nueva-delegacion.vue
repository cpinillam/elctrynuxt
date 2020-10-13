<template>
    <div>
        <loader :successLoader=success :errorLoader=error :loadingLoader=loading ></loader>
         <fieldset :disabled="loading">
        <form method="post" @submit.prevent="enviarMsg" class="mb-5">
            <div class="form-group"><input class="form-control" required type="text" id="ctaName" v-model="ctaName" name="nombre" :placeholder="$t('Componentes.InputsPlaceholder.Nombre_Apellidos')"></div>
            <div class="form-group"><input class="form-control" required type="text" id="ctaHorario" v-model="ctaHorario" name="horario" :placeholder="$t('Componentes.InputsPlaceholder.Horario')"></div>
            <div class="form-group"><input class="form-control" required type="text" id="ctaProvincia" v-model="ctaProvincia" name="provincia" :placeholder="$t('Componentes.InputsPlaceholder.Provincia')"></div>
             <div class="form-group"><input class="form-control" required type="text" id="ctaCiudad" v-model="ctaCiudad" name="ciudad" :placeholder="$t('Componentes.InputsPlaceholder.Ciudad')"></div>
            <div class="form-group"><input class="form-control" required type="tel" id="ctaEmail" v-model="ctaEmail" name="email" :placeholder="$t('Componentes.InputsPlaceholder.Email')"></div>
            <div class="form-group"><input class="form-control" required type="tel" id="ctaPhone" v-model="ctaPhone" name="telefono" :placeholder="$t('Componentes.InputsPlaceholder.Telefono')"></div>
           <div class="form-group selectRadio">
                <h2 class="text-center" >¿Cuentas con un equipo comercial?</h2>
                <label> <input  type="radio" name="equipo" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaEquipo"> {{$t("Jobs.si")}}</label>
                <label> <input  type="radio" name="equipo" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaEquipo"> {{$t("Jobs.no")}}</label>
            </div>

            <div class="form-group selectRadio">
                <h2 class="text-center" >¿Tienes experiencia en el sector energético?</h2>
                <label> <input  type="radio" name="experiencia" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaExperiencia"> {{$t("Jobs.si")}}</label>
                <label> <input  type="radio" name="experiencia" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaExperiencia"> {{$t("Jobs.no")}}</label>
            </div>

            
            <button type="submit" class="btn-cristal-blue mb-2">{{$t("Componentes.InputsPlaceholder.Enviar_candidatura")}}</button>
             
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
        name: "FormNuevaDelegacion",
        components: {
            loader,
            legalTextPolicyJobs,
            legalTextAdvertisingJobs
        },
        data(){
            return {
                ctaName: "",
                ctaHorario: "",
                ctaEmail: "",
                ctaPhone: "",
                ctaProvincia: "",
                ctaCiudad: "",
                ctaExperiencia: "",
                ctaEquipo: "",
                
                ctaCheck: "",

                success: false,
                error: false,
                loading: false
   
            }
        },
        methods: {
            validaMsg(){
                if (this.ctaName && this.ctaPhone && this.ctaHorario && this.ctaCheck){
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
                    bodyFormData.append('provincia', this.ctaProvincia);
                    bodyFormData.append('ciudad', this.ctaCiudad);
                    bodyFormData.append('experiencia', this.ctaExperiencia);
                    bodyFormData.append('equipo', this.ctaEquipo);
                    bodyFormData.append('horario', this.ctaHorario);

                this.axios.post("contact-form-7/v1/contact-forms/129/feedback", bodyFormData, {
                headers: headers
                        })
                .then((response)=> {
                         this.success = true;   
                         location.href="/nueva-delegacion/thanks";                           
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