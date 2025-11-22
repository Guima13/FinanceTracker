<template>
  <div class="text-gray-100">
    <div class="rounded-2xl bg-gray-900/80 border border-white/10 shadow-xl p-4 space-y-4">
      <div class="space-y-1">
        <p class="text-xs uppercase tracking-wide text-teal-300">2025</p>
        <p class="text-sm text-gray-400">Selecione um mês</p>
      </div>

      <ul class="space-y-2">
        <li v-for="mes in meses" :key="mes">
          <button
            @click="selecionarMes(mes)"
            :class="[
              'w-full rounded-xl text-sm font-medium py-2.5 px-3 text-left transition duration-150 ease-in-out border border-transparent',
              mesAtivo === mes
                ? 'bg-teal-600 text-white border-teal-300 shadow-lg shadow-teal-500/30'
                : 'bg-gray-800/80 text-gray-300 hover:text-white hover:border-white/10'
            ]"
          >
            {{ mes }}
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SidebarMeses',
  data() {
    return {
      meses: [
        'Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho',
        'Julho', 'Agosto', 'Setembro', 'Outubro', 'Novembro', 'Dezembro'
      ],
      mesAtivo: 'Janeiro', // Define Janeiro como ativo por padrão
    };
  },
  mounted() {
    // Emite o evento do mês inicial (Janeiro) ao carregar
    this.$emit('mes-selecionado', this.mesAtivo);
  },
  methods: {
    selecionarMes(mes) {
      this.mesAtivo = mes;
      // Emite o evento para a DashboardView filtrar os posts
      this.$emit('mes-selecionado', mes);
    }
  }
}
</script>