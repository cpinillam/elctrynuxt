<template>
    <div>
        <input class="checkbox-cb" id="checkbox-cb" type="checkbox" />
        <div class="cookie-bar">
        <span class="message">
            Utilizamos cookies propias y de terceros para mejorar nuestros servicios y mostrarle publicidad relacionada con sus preferencias mediante el análisis de sus hábitos de navegación.
            Si continúa navegando, consideramos que acepta su uso. Puede cambiar la configuración u obtener más información en nuestra <a target="blank" href="/politica-de-cookies">Politica de Cookies</a></span>
        <span class="mobile">Utilizamos cookies propias y de terceros para mejorar nuestros servicios y mostrarle publicidad relacionada con sus preferencias mediante el análisis de sus hábitos de navegación. <a target="blank" href="/politica-de-cookies">Politica de Cookies</a></span>
        <label for="checkbox-cb" class="close-cb">x</label>
        </div>
    </div>
</template>

<script>
export default {
    name: "cookiesTip"
}
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/cookiesTip/cookiesTip.scss';

</style>