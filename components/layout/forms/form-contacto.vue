<template>
    <div>
        <loader :successLoader=success :errorLoader=error :loadingLoader=loading ></loader>
         <fieldset :disabled="loading">
        <form method="post" @submit.prevent="enviarMsg" class="mb-5">
            
           
                <div class="form-group"><input class="form-control" required type="text" v-model="ctaName" name="nombre" :placeholder="$t('Componentes.InputsPlaceholder.Nombre')"></div>
                <div class="form-group"><input class="form-control" required type="tel" id="ctaEmail" v-model="ctaEmail" name="email" :placeholder="$t('Componentes.InputsPlaceholder.Email')"></div>
                <div class="form-group"><input class="form-control" required type="tel" v-model="ctaPhone" name="telefono" :placeholder="$t('Componentes.InputsPlaceholder.Telefono')"></div>
                <div class="form-group"><input class="form-control" required type="text" id="ctaAsunto" v-model="ctaAsunto" name="asunto" :placeholder="$t('Componentes.InputsPlaceholder.Asunto')"></div>
                 
                  <legalTextPolicy></legalTextPolicy>
                  <legalTextAdvertising></legalTextAdvertising>

            
             <input type="submit" :value="$t('Componentes.InputsPlaceholder.Te_llamamos')" class="btn-cristal-blue mb-2">
                
        </form>
         </fieldset>

    </div>
</template>

<script>

import loader from "../../../components/layout/loader";
import legalTextPolicy from "../../../components/layout/forms/legalTexts/legal-text-policy";
import legalTextAdvertising from "../../../components/layout/forms/legalTexts/legal-text-advertising";

export default {
        name: "FormTrabajaNosotros",
        components: {
            loader,
            legalTextPolicy,
            legalTextAdvertising
        },
        data(){
            return {
                ctaName: "",
                ctaEmail: "",
                ctaPhone: "",
                ctaAsunto: "",
                ctaCheck: "",

                success: false,
                error: false,
                loading: false
   
            }
        },
        methods: {
            validaMsg(){
                if (this.ctaName && this.ctaPhone && this.ctaAsunto && this.ctaCheck){
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
                    bodyFormData.append('asunto', this.ctaAsunto);

                this.axios.post("contact-form-7/v1/contact-forms/75/feedback", bodyFormData, {
                headers: headers
                        })
                .then((response)=> {
                         this.success = true;                            
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
                this.ctaAsunto = "";
                this.ctaCheck = "";
            }
            
           

        }

    }
</script>

<style scoped>

    @import '../../../assets/css/jobs.css';


</style>