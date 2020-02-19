<template>
  <div class="hello">
    <h1>{{ txt1 | deixarMaiusculo }}</h1>
    <h1>{{ txt2 | deixarMaiusculo }}</h1>
    <h1>{{ txt3 | deixarMinusculo }}</h1>
    <h1>{{ txt4 | deixarMinusculo }}</h1>
    <table>  
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Descricao</th>
            <th scope="col">Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="materia in materias" :key="materia.id">
            <td scope="row">{{materia.id}}</td>
            <td>{{materia.descricao}}</td>
            <td v-if="materia.estaCompleta == true" class="completa">{{materia.estaCompleta}}</td>
            <td v-else class="incompleta">{{materia.estaCompleta}}</td>
          </tr>
        </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    //
  },
  data() {
    return {
      txt1:"sou maiúsculo",
      txt2:"sou maiúsculo",
      txt3:"SOU MINÚSCULO",
      txt4:"SOU MINÚSCULO",
      materias: [
        {id: '1', descricao: 'Portugues', estaCompleta: true},
        {id: '2', descricao: 'Matemática', estaCompleta: false},
        {id: '3', descricao: 'Geografia', estaCompleta: false}
        
    ]
  }
  },
  methods: {

  },
  filters: {
    deixarMaiusculo: function (valor){
      return valor.toUpperCase();
    },
    deixarMinusculo: function (valor){
      return valor.toLowerCase();
    }  
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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

.completa{
  color: blue;
}
.incompleta{
  color: red;
}
</style>