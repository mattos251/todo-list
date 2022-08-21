<template>
  <div>

    <v-col cols="12" >
      <v-text-field
        v-model="campoInput"
        label="Qual sua tarefa?"
        outlined
        clearable
        @keyup.enter="handleAddTarefa"
      ></v-text-field>
    </v-col>

    <v-list flat >
      <v-list-item-group multiple active-class="">
        <div v-for="tarefa, index in $store.state.tarefas" :key="index">
            <Tarefa :tarefas="tarefa"/>
        </div>  
      </v-list-item-group>
    </v-list>   
  </div>

</template>

<script>
import Tarefa from "../components/Tarefas/Tarefa.vue"
  export default {
    name: "Home",
    components: {
      Tarefa
    },
    data(){
      return{
        campoInput: null,
       
      }
    },
    methods:{
      handleAddTarefa(){
        this.$store.commit('AdicionaTarefa', this.campoInput)
        this.campoInput = null
      }
    }
  }
</script>

<style scoped>


</style>