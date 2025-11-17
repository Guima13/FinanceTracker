<template>
  <div class="bg-gray-800 text-gray-100 shadow-xl w-28 py-4 rounded-lg border-r border-teal-600/50">
    
    <div class="px-4 pb-3 mb-2 border-b border-gray-700">
      <h3 class="text-lg font-bold text-teal-400">2025</h3>
    </div>

    <nav>
      <ul>
        <li v-for="mes in meses" :key="mes">
          <a 
            href="#" 
            @click.prevent="selecionarMes(mes)" 
            :class="{ 
              'bg-teal-700 text-white font-bold border-l-4 border-teal-400': mesAtivo === mes,
              'text-gray-300 hover:bg-gray-700': mesAtivo !== mes 
            }"
            class="block py-2 px-4 text-sm cursor-pointer transition duration-150 ease-in-out"
          >
            {{ mes }}
          </a>
        </li>
      </ul>
    </nav>
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