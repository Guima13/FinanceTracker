<template>
  <div class="min-h-screen bg-gray-900 text-gray-100 p-8">
    
    <SidebarMeses 
      @mes-selecionado="filtrarPosts" 
      class="fixed left-4 top-1/2 -translate-y-1/2 z-10" 
    />

    <div class="ml-32 md:ml-48 pl-4 pr-4"> 
      
      <h1 class="text-3xl font-bold mb-8 text-teal-400">
        Dashboard de Conteúdo ({{ mesAtivo || 'Todos os Meses' }})
      </h1>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
        <InfoCard title="Total de Posts" value="125" icon="📝" />
        <InfoCard title="Posts no Mês" :value="postsFiltrados.length" icon="📅" />
        <InfoCard title="Visualizações" value="5.2K" icon="👀" />
        <InfoCard title="Engajamento Médio" value="85%" icon="📈" />
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
        
        <div class="lg:col-span-2 bg-gray-800 rounded-lg shadow-xl p-6 h-96">
          <h2 class="text-xl font-semibold mb-4 text-gray-200">
            Performance Mensal
          </h2>
          <div class="flex items-center justify-center h-full text-gray-500">
            [Placeholder: Inserir Componente de Gráfico (e.g., Chart.js)]
          </div>
        </div>

        <div class="lg:col-span-1 bg-gray-800 rounded-lg shadow-xl p-6 flex flex-col justify-between">
          <div>
            <h2 class="text-xl font-semibold mb-4 text-gray-200">
              Mês Ativo: {{ mesAtivo || 'N/A' }}
            </h2>
            <p class="text-4xl font-extrabold text-teal-400">
              {{ postsFiltrados.length }}
            </p>
            <p class="text-sm text-gray-400">Posts Encontrados</p>
          </div>
          <button class="mt-4 w-full bg-teal-600 hover:bg-teal-700 text-white font-bold py-2 px-4 rounded transition">
            Ver Relatório Detalhado
          </button>
        </div>
      </div>
      
      <div class="mt-8 bg-gray-800 rounded-lg shadow-xl p-6">
        <h2 class="text-xl font-semibold mb-4 text-gray-200">
          Posts Recentes ({{ mesAtivo || 'Todos os Meses' }})
        </h2>
        
        <div v-if="postsFiltrados.length > 0">
          <ul class="space-y-2">
            <li v-for="post in postsFiltrados" :key="post.id" class="bg-gray-700 p-3 rounded-md flex justify-between items-center">
              <span class="font-medium text-gray-100">{{ post.title }}</span>
              <span class="text-sm text-teal-400">{{ post.data }}</span>
            </li>
          </ul>
        </div>
        <div v-else class="text-gray-500 text-center py-10">
          Nenhum post encontrado para {{ mesAtivo ? mesAtivo : 'o período selecionado' }}.
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import SidebarMeses from '@/components/SidebarMeses.vue'; 
import InfoCard from '@/components/InfoCard.vue'; // Componente de card simples

export default {
  name: 'DashboardView',
  components: {
    SidebarMeses,
    InfoCard,
  },
  data() {
    return {
      mesAtivo: null,
      // Dados de exemplo (simulando a sua API)
      posts: [
        { id: 1, title: 'Primeiro Post de Janeiro', mes: 'Janeiro', data: '2025-01-15' },
        { id: 2, title: 'Review de Feveveiro', mes: 'Fevereiro', data: '2025-02-01' },
        { id: 3, title: 'Artigo sobre Março', mes: 'Março', data: '2025-03-20' },
        { id: 4, title: 'Post de Abril', mes: 'Abril', data: '2025-04-10' },
        { id: 5, title: 'Segunda Publicação de Janeiro', mes: 'Janeiro', data: '2025-01-28' },
        // Adicione mais posts conforme necessário
      ],
    };
  },
  computed: {
    // Retorna a lista de posts filtrada com base no mêsAtivo
    postsFiltrados() {
      if (!this.mesAtivo) {
        // Se nenhum mês estiver ativo, retorna todos os posts
        return this.posts;
      }
      // Filtra os posts pelo mês correspondente (case-insensitive)
      return this.posts.filter(post => 
        post.mes.toLowerCase() === this.mesAtivo.toLowerCase()
      );
    }
  },
  methods: {
    filtrarPosts(mes) {
      this.mesAtivo = mes;
      // Lógica futura: Você faria aqui uma chamada à API para obter 
      // dados reais (gráficos, cards, etc.) filtrados pelo novo mês.
      console.log('Dashboard a filtrar por:', mes);
    }
  }
}
</script>