<template>
  <div>
    <button  class="waves-effect waves-light btn-large boton" v-on:click="mostrar_ninja()">Ninja</button>
    <button  class="waves-effect waves-light btn-large boton" v-on:click="mostrar_gato()">Gato  </button>
     <!-- Modalcito-->
    <div id="modal1" class="modal">
        <div class="modal-content">
          <h4>Seleccionaste:</h4>
          <p>{{this.imagen}}</p>
          <img id="imagen_modal" :src="require('@/assets/' + this.imagen +'.jpg')" alt="">
        </div>
        <div class="modal-footer">
        <a href="#!" class="modal-close waves-effect waves-light btn">Cerrar</a>
        </div>
    </div>
    </div>
</template>

<script>
import M from 'materialize-css'
export default {
  name: 'NinjaGato',
  data: function(){
    return{
      imagen:"gastito"
    }
  },
  methods: {
    mostrar_ninja(){
      this.imagen="ninja";
    },
    mostrar_gato(){
      this.imagen="gato";
    }
  },
  mounted: function(){
      M.AutoInit();
  },
  beforeUpdate() {
    // alert(this.imagen)
    const modal = document.querySelector('.modal')
    var instance = M.Modal.getInstance(modal);
    instance.open();
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
body{
  font-family: 'Ubuntu', sans-serif;
}
.boton{
  margin: 20px;
}
#imagen_modal{
  width: 200px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
