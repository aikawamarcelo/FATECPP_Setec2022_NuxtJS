<template>
    <section>

<!--
<p>Lista de Alunos:</p>

<p v-for=" (aluno, i) in listaAlunos" key="i">
    {{i}} - {{aluno}}
</p>

<p>Exibir Notas:</p>

<div v-if="exibirNota">

<p>Notas</p>

</div>

<div v-else>

<p>Não Exibir Nota:</p>

</div>
-->

  <input type="text" v-model="aluno">
  <button @click="adicionarAluno(aluno)">
      Adicionar aluno
  </button>

    <p>Primeiro da Turma: {{primeiroDaTurma}}</p>

    <hr>

    <Alunos :lista="listaAlunos"
    @remover ="removerAluno"
    />

    </section>
      </template>
          <script>
              export default {
               name: 'IndexPage',
               head(){
               return{
               title: "HOME"
              }
               },
               data(){
               return{
               aluno: "",
               listaAlunos: [
               {
               id: "1",
               name: "Lucas"
               },
               {
               id: "2",
               name: "Wesley"
               },
               ],
               exibirNota: true
               };
             },
    methods: {
     adicionarAluno(aluno){
      
      Object.assign(alunos, {
        id:3,
        name: aluno
      });
      this.listaAlunos.push(aluno)
      this.aluno = ""
    },

     removerAluno(aluno){
      alert("Remover aluno: " + aluno.name)
    }

  },
  computed: {
    primeiroDaTurma(){
      //logico
      return this.listaAlunos[0].name
    }
  },
  watch: {
    listaAlunos(novoValor, velhoValor){
      alert("Lista foi alterada.")
    },

    asyncData(){
    
    },

    created(){

    },

    mounted(){

    }
  }
}
</script>

<style >

  section{
    background-color:antiquewhite;
  }

</style>