<template>
     <div class="form-group form-line-legal mt-1 ">
        <input type="checkbox" required class="mr-1">
        {{$t("Componentes.legalPolicy.legal_text_advertising_text")}} <strong><a :href="$t('Routes.politica_de_privacidad')" target="_blank" class="ml-1"> {{$t("Componentes.legalPolicy.politica_de_privacidad")}}</a></strong>
        </div>
</template>

<script>
export default {
    name: "legalTextAdvertising"
}
</script>

<style scoped>
.form-line-legal {
  text-align: justify;
  width: 90%;
  position: relative;
  max-width: 550px;
  margin-left: auto;
  margin-right: auto;
  font-size: 11px;
}
</style>