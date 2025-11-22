<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-950 via-gray-900 to-gray-950 text-gray-100 relative overflow-hidden">
    <div class="absolute inset-0 opacity-30 pointer-events-none">
      <div class="w-72 h-72 bg-teal-500/30 blur-3xl rounded-full absolute -top-10 -left-8"></div>
      <div class="w-96 h-96 bg-cyan-400/20 blur-3xl rounded-full absolute top-32 right-0"></div>
    </div>

    <div class="relative w-full max-w-screen-2xl mx-auto px-4 sm:px-10 lg:px-20 py-12">
      <div class="flex flex-col lg:flex-row gap-8">
        <aside class="lg:w-56 xl:w-64 flex-shrink-0">
          <div class="sticky top-6">
            <SidebarMeses @mes-selecionado="filtrarPosts" />
          </div>
        </aside>

        <div class="flex-1 space-y-12">
          <section class="rounded-3xl bg-gray-900/70 border border-white/10 p-8 shadow-2xl space-y-4">
            <p class="text-sm uppercase tracking-wider text-teal-300 font-semibold">Visão geral</p>
            <h1 class="text-3xl sm:text-4xl font-bold text-white">
              Dashboard de Conteudo ({{ mesAtivo || 'Todos os Meses' }})
            </h1>
            <p class="text-gray-300 max-w-2xl">
              Escolha um mês e veja os seus gastos mensais.
            </p>
            <div class="flex flex-wrap gap-4">
              <div class="rounded-2xl bg-gray-800/80 border border-white/5 px-4 py-3">
                <p class="text-xs uppercase tracking-wide text-gray-400">Mês ativo</p>
                <p class="text-xl font-semibold text-white mt-1">{{ mesAtivo || 'Todos os meses' }}</p>
              </div>
              <div class="rounded-2xl bg-gray-800/80 border border-white/5 px-4 py-3">
                <p class="text-xs uppercase tracking-wide text-gray-400">Gastos inseridos</p>
                <p class="text-xl font-semibold text-teal-300 mt-1">{{ postsFiltrados.length }}</p>
              </div>
            </div>
            <div class="flex flex-wrap gap-3 pt-2">
              <button class="inline-flex items-center px-5 py-2.5 rounded-2xl bg-teal-500 text-gray-900 font-semibold shadow-lg shadow-teal-500/30 hover:bg-teal-400 transition">
                Nova publicacao
              </button>
              <button class="inline-flex items-center px-5 py-2.5 rounded-2xl border border-white/15 text-gray-100 hover:bg-white/5 transition">
                Ver relatorio mensal
              </button>
            </div>
          </section>

          <section class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 gap-6">
        <div class="rounded-2xl bg-gray-900/70 border border-white/5 shadow-xl p-6 space-y-1">
          <p class="text-sm text-gray-400">Total de gastos</p>
          <p class="text-3xl font-bold text-white">125</p>
          <p class="text-sm text-teal-300">+8 esta semana</p>
        </div>
        <div class="rounded-2xl bg-gray-900/70 border border-white/5 shadow-xl p-6 space-y-1">
          <p class="text-sm text-gray-400">Gastos no mês</p>
          <p class="text-3xl font-bold text-white">{{ postsFiltrados.length }}</p>
          <p class="text-sm text-teal-300">-2 vs último mês</p>
        </div>
        <div class="rounded-2xl bg-gray-900/70 border border-white/5 shadow-xl p-6 space-y-1">
          <p class="text-sm text-gray-400">Metas criadas mensalmente</p>
          <p class="text-3xl font-bold text-white">3</p>
          <p class="text-sm text-teal-300">+18% </p>
        </div>
        <div class="rounded-2xl bg-gray-900/70 border border-white/5 shadow-xl p-6 space-y-1">
          <p class="text-sm text-gray-400">Metas concluídas</p>
          <p class="text-3xl font-bold text-white">2</p>
          <p class="text-sm text-teal-300">33%</p>
        </div>
          </section>

          <section class="grid grid-cols-1 lg:grid-cols-3 gap-6">
        <div class="lg:col-span-2 rounded-3xl bg-gray-900/70 border border-white/5 shadow-2xl p-8 flex flex-col gap-6">
          <div class="flex items-center justify-between">
            <div>
              <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Performance mensal</p>
              <h2 class="text-2xl font-bold text-white mt-2">Tendencia de alcance</h2>
            </div>
            <button class="text-sm text-gray-400 border border-white/10 px-4 py-2 rounded-xl hover:bg-white/5 transition">
              Exportar dados
            </button>
          </div>
          <div class="flex-1 border border-dashed border-white/10 rounded-2xl backdrop-blur flex items-center justify-center text-gray-500 text-sm min-h-[18rem]">
            colocar um gráfico
          </div>
        </div>

        <div class="rounded-3xl bg-gray-900/80 border border-white/5 shadow-2xl p-8 space-y-6">
          <div>
            <p class="text-sm text-gray-400">Progresso editorial</p>
            <p class="text-3xl font-bold text-white mt-2">{{ mesAtivo || 'Todos os meses' }}</p>
          </div>
          <div>
            <p class="text-sm text-gray-400">Percentual </p>
            <div class="mt-3 bg-gray-800 rounded-full h-3 overflow-hidden">
              <div class="h-full bg-gradient-to-r from-teal-400 to-cyan-400 w-4/5"></div>
            </div>
            <p class="text-sm text-gray-400 mt-2">80% do mês concluido</p>
          </div>
          <div class="space-y-2 text-sm text-gray-300">
            <p class="text-xs tracking-wide text-gray-400 uppercase">Ultimas transacoes inseridas</p>
            <div class="rounded-2xl bg-gray-800/60 border border-white/5 p-3">
              <p class="text-white font-semibold">-70€ em gasolina</p>
              <p class="text-teal-300">Hoje</p>
            </div>
            <div class="rounded-2xl bg-gray-800/60 border border-white/5 p-3">
              <p class="text-white font-semibold">-6.99€ em Alimentação</p>
              <p class="text-teal-300">Ontem</p>
            </div>
            <div class="rounded-2xl bg-gray-800/60 border border-white/5 p-3">
              <p class="text-white font-semibold">-17.99€ em Vestuário</p>
              <p class="text-teal-300">Há 3 dias atrás</p>
            </div>
          </div>
        </div>
          </section>

          <section class="grid grid-cols-1 lg:grid-cols-2 gap-6">
        <div class="rounded-3xl bg-gray-900/70 border border-white/5 shadow-2xl p-8 space-y-6">
          <div class="flex items-center justify-between">
            <div>
              <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Total de gastos inseridos</p>
              <h2 class="text-2xl font-bold text-white mt-2">({{ mesAtivo || 'Todos os meses' }})</h2>
            </div>
            <span class="text-sm text-gray-400">{{ postsFiltrados.length }} resultados</span>
          </div>

          <div v-if="postsFiltrados.length > 0" class="space-y-3">
            <div
              v-for="post in postsFiltrados"
              :key="post.id"
              class="rounded-2xl bg-gray-800/80 border border-white/5 p-4 flex flex-col sm:flex-row sm:items-center sm:justify-between gap-3"
            >
              <div>
                <p class="text-white font-semibold">{{ post.title }}</p>
                <p class="text-sm text-gray-400">Mes: {{ post.mes }}</p>
              </div>
              <span class="text-sm text-teal-300">{{ post.data }}</span>
            </div>
          </div>
          <div v-else class="text-gray-500 text-center py-10">
            colocar posts simulados {{ mesAtivo ? mesAtivo : 'o periodo selecionado' }}.
          </div>
        </div>

        <div class="rounded-3xl bg-gray-900/70 border border-white/5 shadow-2xl p-8 space-y-6">
          <div>
            <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Checklist rapido</p>
            <h2 class="text-2xl font-bold text-white mt-2">Alertas de budgets</h2>
          </div>
          <ul class="space-y-4">
            <li class="flex items-start gap-3">
              <span class="h-6 w-6 rounded-full bg-teal-500/20 text-teal-300 flex items-center justify-center text-sm font-semibold">1</span>
              <div>
                <p class="text-white font-semibold">ahdahda</p>
                <p class="text-gray-400 text-sm">313123123.</p>
              </div>
            </li>
            <li class="flex items-start gap-3">
              <span class="h-6 w-6 rounded-full bg-teal-500/20 text-teal-300 flex items-center justify-center text-sm font-semibold">2</span>
              <div>
                <p class="text-white font-semibold">tecxtoo31312</p>
                <p class="text-gray-400 text-sm">texto 313131.</p>
              </div>
            </li>
            <li class="flex items-start gap-3">
              <span class="h-6 w-6 rounded-full bg-teal-500/20 text-teal-300 flex items-center justify-center text-sm font-semibold">3</span>
              <div>
                <p class="text-white font-semibold">texto 1231231</p>
                <p class="text-gray-400 text-sm">texto 2756643.</p>
              </div>
            </li>
          </ul>
          <div class="rounded-2xl bg-teal-500/10 border border-teal-400/30 p-4 text-sm text-teal-100">
            alguma ideia para colocar aqui
          </div>
        </div>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SidebarMeses from '@/components/SidebarMeses.vue'; 

export default {
  name: 'DashboardView',
  components: {
    SidebarMeses,
  },
  data() {
    return {
      mesAtivo: null,
      posts: [
        { id: 1, title: 'Primeiro Post de Janeiro', mes: 'Janeiro', data: '2025-01-15' },
        { id: 2, title: 'Review de Feveveiro', mes: 'Fevereiro', data: '2025-02-01' },
        { id: 3, title: 'Artigo sobre Marco', mes: 'Marco', data: '2025-03-20' },
        { id: 4, title: 'Post de Abril', mes: 'Abril', data: '2025-04-10' },
        { id: 5, title: 'Segunda Publicacao de Janeiro', mes: 'Janeiro', data: '2025-01-28' },
      ],
      timeline: [
        { id: 1, titulo: 'Reuniao editorial', dia: 'Seg', horario: '14h', status: 'Rever temas' },
        { id: 2, titulo: 'Revisao de copys', dia: 'Qua', horario: '10h', status: 'Aprovar textos' },
        { id: 3, titulo: 'Live mensal', dia: 'Qui', horario: '19h', status: 'Briefing final' },
        { id: 4, titulo: 'Envio newsletter', dia: 'Sex', horario: '08h', status: 'Segmentar base' },
      ],
      canaisDestaque: [
        { nome: 'Blog', percentual: 78 },
        { nome: 'Instagram', percentual: 64 },
        { nome: 'Newsletter', percentual: 55 },
        { nome: 'YouTube', percentual: 42 },
      ],
    };
  },
  computed: {
    postsFiltrados() {
      if (!this.mesAtivo) {
        return this.posts;
      }
      return this.posts.filter(post => 
        post.mes.toLowerCase() === this.mesAtivo.toLowerCase()
      );
    }
  },
  methods: {
    filtrarPosts(mes) {
      this.mesAtivo = mes;
      console.log('Dashboard a filtrar por:', mes);
    }
  }
}
</script>
