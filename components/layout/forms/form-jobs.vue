<template>
    <div>
      
         <fieldset :disabled="loading">
        <form method="post" @submit.prevent="validaMsg" class="mb-5 text-center">
            <div class="form-group"><input class="form-control" required type="text" id="ctaName" v-model="ctaName" name="nombre" :placeholder="$t('Componentes.InputsPlaceholder.Nombre')"></div>
            <div class="form-group"><input class="form-control" required type="text" id="ctaPuesto" v-model="ctaPuesto" name="puesto" :placeholder="$t('Componentes.InputsPlaceholder.ultimo_puesto')"></div>
            <div class="form-group"><input class="form-control" required type="text" id="ctaHorario" v-model="ctaHorario" name="horario" :placeholder="$t('Componentes.InputsPlaceholder.Horario')"></div>
            <div class="form-group"><input class="form-control" required type="tel" id="ctaEmail" v-model="ctaEmail" name="email" :placeholder="$t('Componentes.InputsPlaceholder.Email')"></div>
            <div class="form-group"><input class="form-control" required type="tel" id="ctaPhone" v-model="ctaPhone" name="telefono" :placeholder="$t('Componentes.InputsPlaceholder.Telefono')"></div>
            <div class="form-group"><input class="form-control" required type="text" id="ctaCiudad" v-model="ctaCiudad" name="ciudad" :placeholder="$t('Componentes.InputsPlaceholder.Ciudad')"></div>
            
            <selectFile v-model="file" @newfile="fileEmpty" :cvempty="CVempty"></selectFile>
          
            <div class="form-group selectRadio">
                <h2 class="text-center" >{{$t("Jobs.Form_trabaja_experiencia_comercial")}}</h2>
                <label> <input required  type="radio" name="comercialventas" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaComercialVentas"> {{$t("Jobs.si")}}</label>
                <label> <input required type="radio" name="comercialventas" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaComercialVentas"> {{$t("Jobs.no")}}</label>
            </div>
            
            <div class="form-group selectRadio">
                <h2 class="text-center" >{{$t("Jobs.Form_trabaja_experiencia_sector")}}</h2>
                <label> <input required  type="radio" name="experiencia" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaExperiencia"> {{$t("Jobs.si")}}</label>
                <label> <input required type="radio" name="experiencia" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaExperiencia"> {{$t("Jobs.no")}}</label>
            </div>

            

            <div class="form-group selectRadio">
                <h2 class="text-center" >{{$t("Jobs.Form_trabaja_experiencia_equipo")}}</h2>
                <label> <input required type="radio" name="gestionequipos" class="radio-form-trabaja" :value="$t('Jobs.si')" v-model="ctaGestion"> {{$t("Jobs.si")}}</label>
                <label> <input required type="radio" name="gestionequipos" class="radio-form-trabaja" :value="$t('Jobs.no')" v-model="ctaGestion"> {{$t("Jobs.no")}}</label>
            </div>
            
            <button type="submit" class="btn-cristal-blue mb-2">{{$t("Componentes.InputsPlaceholder.Enviar_candidatura")}}</button>
            
             <legalTextPolicyJobs></legalTextPolicyJobs>
             <legalTextAdvertisingJobs></legalTextAdvertisingJobs>
        </form>
         </fieldset>
           <loader :successLoader=success :errorLoader=error :loadingLoader=loading ></loader>
    </div>
</template>

<script>

import loader from "../../../components/layout/loader";
import selectFile from "../../../components/layout/forms/select-file";
import legalTextPolicyJobs from "../../../components/layout/forms/legalTexts/legal-text-policy-jobs";
import legalTextAdvertisingJobs from "../../../components/layout/forms/legalTexts/legal-text-advertising-jobs";

export default {
        name: "FormJobs",
        components: {
            loader, 
            selectFile,
            legalTextPolicyJobs,
            legalTextAdvertisingJobs
        },
        props: {
            oferta : String

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
                ctaComercialVentas: "",
                ctaHorario: "",
                ctaCheck: "",

                CVempty: false,
                file: null,

                success: false,
                error: false,
                loading: false,
                formulario: {},
   
            }
        },
       
        methods: {

            validaMsg(){
                if (this.file){
                    
                    this.enviarMsg();    
                }
                else {
                    this.CVempty = true;
                    alert("Falta adjuntar CV"); 
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
                    bodyFormData.append('horario', this.ctaHorario);
                    bodyFormData.append('ciudad', this.ctaCiudad);
                    bodyFormData.append('experiencia', this.ctaExperiencia);
                    bodyFormData.append('comercialventas', this.ctaComercialVentas);
                    bodyFormData.append('gestion', this.ctaGestion);
                    bodyFormData.append('oferta', this.oferta);
                    bodyFormData.append('cv', this.file);

                this.axios.post("contact-form-7/v1/contact-forms/137/feedback", bodyFormData, {
                headers: headers
                        })
                .then((response)=> {
                         this.success = true;                            
                         location.href="/jobs/gracias";  
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
            },

            fileEmpty(){
                this.file = true;
                this.CVempty = false;
            }
            
           

        }

    }
</script>

<style scoped>

    @import '../../../assets/css/jobs.css';


</style>