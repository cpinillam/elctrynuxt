<template>
<div id="ctaForm">

    <loader :successLoader=success :errorLoader=error :loadingLoader=loading ></loader>

    <form method="post" @submit.prevent="enviarMsg" autocomplete="off">

 

            <fieldset :disabled="loading">
            <div class="form-group form-line-call-us">
                <div class="input-call-us-main form-left "><input id="ctaName" v-model="ctaName" type="text" class="input-call-us  form-left" :placeholder="$t('Componentes.InputsPlaceholder.Nombre')" required autocomplete="off"/></div>
                <div class="form-center input-call-us-main"><input id="ctaPhone" v-model="ctaPhone" type="tel" class="input-call-us" :placeholder="$t('Componentes.InputsPlaceholder.Telefono')" required  autocomplete="off"/></div>
                
                <button type="submit" class="btn-call-us">{{$t('Componentes.InputsPlaceholder.Te_llamamos')}}</button>
                
            </div>
            </fieldset>
            
            <legalTextPolicy></legalTextPolicy>
            <legalTextAdvertising></legalTextAdvertising>
              
    </form>

</div>
</template>

<script>
import loader from "../../../components/layout/loader";
import legalTextPolicy from "../../../components/layout/forms/legalTexts/legal-text-policy";
import legalTextAdvertising from "../../../components/layout/forms/legalTexts/legal-text-advertising";

    export default {
        name: "form-cta-phone",
        components:{
            loader,
            legalTextPolicy,
            legalTextAdvertising
            
        },
        data(){
            return {
                success: false,
                error: false,
                loading: false,

                ctaName: "",
                ctaPhone: "",
                ctaCheck: "",   
                ctaCheck2: ""   
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

                this.axios.post("contact-form-7/v1/contact-forms/72/feedback", bodyFormData, {
                headers: headers })
                .then((response)=> {
                            this.success = true;                          
                            setTimeout(this.reset, 5000);


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

        },
    }
</script>

<style lang="sass"  scoped>
    @import '../../../assets/css/form-line-call-us.scss';
</style>
