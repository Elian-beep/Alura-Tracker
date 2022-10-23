<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulario para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa deseja fazer hoje?"
        />
      </div>

      <div class="column">
        <TemporizadorForm />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorForm from './TemporizadorForm.vue';

export default defineComponent({
  name: "FormularioPrincipal",
  components: { TemporizadorForm },
});
</script>

<style></style>