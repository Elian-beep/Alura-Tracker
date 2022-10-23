<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">{{ tarefa?.descricao }}</div>
      <div class="column">
        <CronometroForm :tempoEmSegundos="tarefa?.duracaoEmSegundos" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import ITarefa from "@/interfaces/ITarefa";
import { defineComponent, PropType } from "vue";
import CronometroForm from "./CronometroForm.vue";

export default defineComponent({
  name: "TarefaVue",
  components: { CronometroForm },
  props: {
    tarefa: {
        type: Object as PropType<ITarefa>,
        requiered: true
    }
  }
});
</script>

<style scoped>
.box {
  background: #faf0ca;
}
</style>