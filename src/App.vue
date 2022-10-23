<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <FormularioPrincipal @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <TarefaVue
          v-for="(tarefa, index) in tarefas"
          :key="index"
          :tarefa="tarefa"
        />
        <BoxVue v-if="listaEstaVazia"> Você não está muito produtivo hoje :(</BoxVue>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BarraLateral from "@/components/BarraLateral.vue";
import FormularioPrincipal from "@/components/FormularioPrincipal.vue";
import TarefaVue from "./components/TarefaVue.vue";
import ITarefa from "./interfaces/ITarefa";
import BoxVue from "./components/BoxVue.vue";

export default defineComponent({
  name: "App",
  components: { BarraLateral, FormularioPrincipal, TarefaVue, BoxVue },
  data() {
    return {
      tarefas: [] as ITarefa[],
    };
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    },
  },
  computed:{
    listaEstaVazia() : boolean{
      return this.tarefas.length == 0 //Retorna true se a lista estiver vazia
    }
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>