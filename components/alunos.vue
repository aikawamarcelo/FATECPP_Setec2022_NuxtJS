<template>
    <div>
        <p>COMPONENTE: lista de alunos</p>
        <p v-for="aluno in lista">
            {{ aluno.name }} - {{aluno.id}}
            <button @click="remover(aluno)">Remover Aluno</button>      
        </p>
       
    </div>
</template>

<script>
     export default{
           name: "alunos",
           props: {
               lista: {
                 type: Object,
                 required: true
               }
           },
           methods:{
            remover(aluno){
                this.$emit('remover',aluno)
            }
           }
    }
</script>     