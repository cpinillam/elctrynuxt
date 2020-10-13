<template>
     <div class="loader" v-if="loadingLoader"></div>
</template>


<style scoped>

.loader{  /* Loader Div Class */
    position: absolute;
    top:0px;
    right:0px;
    width:100%;
    height:100%;

    background-image: url(../../../assets/img/images/loader.svg);
    background-color: rgba(241, 248, 253, 0.0);
    background-size: 100px;
    background-repeat:no-repeat;
    background-position:center;
    z-index:10000000;
 
}
</style>