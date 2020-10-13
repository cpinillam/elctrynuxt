<template>
    
           <div class="modal fade" :id=id tabindex="-1" role="dialog" aria-labelledby="basicModal" aria-hidden="true">
                
               <div class="modal-dialog">
                   <div class="modal-content">
                       <div class="modal-header">
                           <img src="../../../assets/img/anima-mail.svg">
                           <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                               <span aria-hidden="true">&times;</span>
                           </button>

                       </div>
                       <div class="modal-body">
                           <loader :successLoader=success :errorLoader=error :loadingLoader=loading ></loader>
                           <p>{{$t("Componentes.Modal.Solicitar_informacion_de")}}</p>
                           <h3>{{servicio}}</h3>
                            <fieldset :disabled="loading">
                           <form method="post" @submit.prevent="enviarMsg">
                               <div class="form-group"><input class="form-control" type="text" id="ctaName" v-model="ctaName" :placeholder="$t('Componentes.InputsPlaceholder.Nombre')" required></div>
                               <div class="form-group"><input class="form-control" type="tel" id="ctaPhone" v-model="ctaPhone" :placeholder="$t('Componentes.InputsPlaceholder.Telefono')" required></div>
                               
                              <legalTextPolicyJobs></legalTextPolicyJobs>
                              <legalTextAdvertisingJobs></legalTextAdvertisingJobs>
                                <input type="submit" :value="$t('Componentes.InputsPlaceholder.Enviar')" class="btn btn-primary">
                           </form>
                            </fieldset>


                       </div>
                       <div class="modal-footer">
                           
                          
                       </div>
                   </div>
               </div>
           </div>
</template>

<script>
import loader from "../../../components/layout/loader";
import legalTextPolicyJobs from "../../../components/layout/forms/legalTexts/legal-text-policy-jobs";
import legalTextAdvertisingJobs from "../../../components/layout/forms/legalTexts/legal-text-advertising-jobs";

export default {
    name: "formEquipo",
    components:{
            loader,
            legalTextPolicyJobs,
            legalTextAdvertisingJobs
        },
    props: {
        id: String,
        servicio: String
    },
        data(){
            return {
                success: false,
                error: false,
                loading: false,

                ctaName: "",
                ctaPhone: "",
                ctaCheck: ""   
            }
        },

        
        methods: {
            validaMsg(){
                if (this.ctaName && this.ctaPhone && this.ctaCheck){
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
                    bodyFormData.append('servicio', this.servicio);

                this.axios.post("contact-form-7/v1/contact-forms/73/feedback", bodyFormData, {
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
                this.ctaCheck = "";
            }

        }
}
</script>

<style scoped>
    @import '../../../assets/css/modal-custom.css';
</style>
