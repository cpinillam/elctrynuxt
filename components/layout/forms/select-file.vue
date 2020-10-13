<template>
  <label class="file-select">
    <div class="select-button">
      <span v-if="UploadFile">✔️ {{$t("Componentes.InputsPlaceholder.Archivo")}}: {{UploadFile}}</span> 
      <span v-else>📑  {{$t("Componentes.InputsPlaceholder.Adjuntar")}}</span>
      
    </div>

    <p v-if=!UploadFile>{{$t("Componentes.InputsPlaceholder.FORMATO")}}</p>
   <div v-if=cvempty class="alert alert-danger" role="alert">  Campo Obligatorio </div>
  
    <input type="file" @change="handlefilechange" accept="application/pdf"/>
  </label>
</template>

<script>
export default {
  data(){
    return {
      UploadFile: null
    }
  },
  props: {
    value: File,
    cvempty : Boolean
  },

  methods: {
    handlefilechange(e) {
      
      var newFile = e.target.files[0];
      
      
      if (newFile.type === 'application/pdf'){
        this.UploadFile = newFile.name;
        this.$emit('newfile', newFile);
        
        
         
     }
     else {
        alert('Solo se permiten archivos PDF');
     }
      
     
    }
  }
}
</script>

<style scoped>
.file-select > .select-button {
  padding: 1rem;

  color: white;
  background-color: #c4c4c4;

  border-radius: .5rem;

  text-align: center;
  font-weight: bold;
}

.file-select > input[type="file"] {
  display: none;
}
</style>