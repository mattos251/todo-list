<template>
  <div>

    <v-list
      flat
    >

      <v-list-item-group
        v-model="settings"
        multiple
        active-class=""
      >
      <Tarefa />  
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
    } 
}
</script>
