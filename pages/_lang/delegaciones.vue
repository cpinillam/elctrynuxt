<template>
<div>
   <loader :errorLoader=error :loadingLoader=loading ></loader>
    <div class="block-titel mb-4">
            <div class="d-flex justify-content-between container">
                <div class="pl-4 pl-sm-2 pl-md-0">
                    <h1>{{$t("Delegaciones.Delegaciones")}}<br></h1>
                    <p>{{$t("Delegaciones.Delegaciones_subtitulo")}}</p>
                </div>
                <div class="d-none d-md-inline puntos"></div>
            </div>
        </div>

  <div style="height: 50vh; width: 100%">
   
    <l-map
      v-if="showMap"
      :zoom="zoom"
      :center="center"
      :options="mapOptions"
      style="height: 100%"
      @update:center="centerUpdate"
      @update:zoom="zoomUpdate"
    >
      <l-tile-layer
        :url="url"
        :attribution="attribution"
      />

       <l-marker v-for="(itemDelegacion, index) in delegacionesList" :key="index" :lat-lng="itemDelegacion.marker">
        <l-icon 
            :icon-url=ElectryIcon
        />
        <l-popup>
          <div @click="innerClick">
            {{itemDelegacion.title}}
           
          </div>
        </l-popup>
      </l-marker>
    </l-map>
  </div>

<div id="delegaciones-column" class="ligth">
                <div class="row d-lg-flex justify-content-lg-center">
                    <div class="col-11 mb-5">
                        <div class="delegaciones-column bg-secondary">
                            <div class="container">
                                <div class="row">
                                    <div class="col-12 d-flex flex-column align-items-center justify-content-lg-center">
                                        <h2>{{$t("Delegaciones.cta_crea_delegacion_titulo")}}<br></h2>
                                        <p class="pt-3 small text-center w-50">{{$t("Delegaciones.cta_crea_delegacion_texto")}}<br></p>
                                        <a class="enlace-electry" href="nueva-delegacion"><button class="btn-cristal-blue">{{$t("Componentes.Botones.Mas_informacion")}}</button></a></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
</div>
</template>

<script>
import loader from "../../components/layout/loader.vue";

    import { latLng } from "leaflet";
    import { LMap, LTileLayer, LMarker, LPopup, LTooltip, LIcon } from "vue2-leaflet";
    import iconElectry from '../../assets/img/images/marker-icon.png'


export default {
  name: "Delegaciones",         
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LTooltip,
    LPopup,
    LIcon,
    loader
  },

  
  data() {
    return {
      error: false,
      loading: false,
      ElectryIcon: iconElectry,      
      delegacionesList:[],
      zoom: 5,
      center: latLng(40.38002840251183, -3.6914062500000004),
      url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      attribution:
        '&copy; <a class="enlace-electry" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
     withPopup2:[ latLng(47.41322, -1.219482),],
     withPopup: latLng(47.41322, -1.219482),
     marker:{
         "lat":"40.40094763151963",
         "lng":"-3.6941528320312504"
     },
     markers:[
          {
              "marker": latLng(47.41322, -1.219482),
              "nombre": "test"
          },
          {
              "marker": latLng(49.41322, -1.419482),
              "nombre": "test",
          },
        

          ],
      currentZoom: 11.5,
      currentCenter: latLng(47.41322, -1.219482),
      mapOptions: {
        zoomSnap: 0.5
      },
      showMap: true
    };
  },

  created() {
            this.getDelegaciones();
           
            },

  methods: {
    zoomUpdate(zoom) {
      this.currentZoom = zoom;
    },
    centerUpdate(center) {
      this.currentCenter = center;
    },
    showLongText() {
      this.showParagraph = !this.showParagraph;
    },
    innerClick() {
      //alert("Click!");
    },

    async getDelegaciones(){
      this.loading = true;
            this.axios('wp/v2/delegaciones')
               .then((response) =>{
                 this.loading = false;
                  
                   response.data.forEach(element => {
                            let item = {};
                            item.id = element.ID;
                            item.title = element.post_title;
                            item.mapa = element.delegacion.mapa;   
                            item.latitud = element.delegacion.mapa.match("leaflet-marker lat=(.+?)lng=")[1];  
                            item.longitud = element.delegacion.mapa.match("lng=(.+?)]")[1];            
                            item.marker = latLng(item.latitud, item.longitud);

                          
                            
                            this.delegacionesList.push(item);
                        });

                   
                })
                 .catch ((error)=> {
                     
                        console.log(error);
                    });

                   
                   
                } 
  }
};
</script>