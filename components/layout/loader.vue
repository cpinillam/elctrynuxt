<template>
	<div>
		
		<div class="loader" v-if="loadingLoader"></div>
            
    <div v-if="successLoader" class="col-12 d-flex justify-content-center" style="z-index:5;" >
        <div class="alert alert-success col-8 position-absolute" role="alert">
                {{$t("Componentes.InputsPlaceholder.gracias")}} 🎉
            </div>
    </div>

    <div v-if="errorLoader" class="col-12 d-flex justify-content-center" style="z-index:5;" >
        <div class="alert alert-warning col-8 position-absolute" role="alert">
                🤷‍♂️  {{$t("Componentes.InputsPlaceholder.error")}} <a href="mailto:info@electryconsulting.com"> info@electryconsulting.com </a>
            </div>
    </div>

	</div>
</template>

<script>
export default {
	name:"loader",
	props: {
		successLoader: Boolean,
        errorLoader: Boolean,
        loadingLoader: Boolean,
	},

}
</script>

<style scoped>

.loader{  /* Loader Div Class */
    position: absolute;
    top:0px;
    right:0px;
    width:100%;
    height:100%;

    background-image: url(../../assets/img/images/loader.svg);
    background-color: rgba(241, 248, 253, 0.7);
    background-size: 100px;
    background-repeat:no-repeat;
    background-position:center;
    z-index:10000000;
 
}
</style>