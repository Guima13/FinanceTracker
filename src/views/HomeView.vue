<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-950 via-gray-900 to-gray-950 text-gray-100">
    <main class="relative overflow-hidden">
      <div class="absolute inset-0 opacity-30 pointer-events-none">
        <div class="w-72 h-72 bg-teal-500/40 blur-3xl rounded-full absolute -top-20 -left-10"></div>
        <div class="w-96 h-96 bg-cyan-400/30 blur-3xl rounded-full absolute top-40 right-0"></div>
      </div>

      <section class="relative max-w-6xl mx-auto px-6 lg:px-10 pt-16 pb-20">
        <div class="text-center space-y-6 bg-gray-900/70 border border-white/5 rounded-3xl p-10 backdrop-blur-xl shadow-2xl">
          <p class="inline-flex items-center px-4 py-1 rounded-full text-sm font-medium bg-teal-500/10 text-teal-300 border border-teal-500/20">
            Simplifique as suas financas
          </p>

          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold leading-tight">
            Domine o seu dinheiro com um dashboard <span class="text-teal-300">inteligente</span>
          </h1>

          <p class="text-lg sm:text-xl text-gray-300 max-w-3xl mx-auto">
            Controle transacoes, defina orcamentos e veja insights claros sobre os seus gastos em um unico lugar, com visual inspirado no dashboard.
          </p>

          <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
            <a
              href="/login"
              class="w-full sm:w-auto inline-flex items-center justify-center px-8 py-3 rounded-xl font-semibold bg-teal-500 text-gray-900 hover:bg-teal-400 transition-colors duration-200 shadow-lg shadow-teal-500/30"
            >
              Comecar agora
            </a>
            <a
              href="#features"
              class="w-full sm:w-auto inline-flex items-center justify-center px-8 py-3 rounded-xl font-semibold border border-white/20 text-gray-100 hover:bg-white/5 transition-colors duration-200"
            >
              Ver funcionalidades
            </a>
          </div>

          <div class="mt-10">
            <div class="relative overflow-hidden rounded-2xl border border-white/10 bg-gradient-to-br from-gray-900/70 to-gray-900 shadow-xl">
              <div class="absolute inset-0 bg-gradient-to-r from-teal-500/10 via-transparent to-cyan-500/10"></div>
              <img
                class="w-full h-auto object-cover opacity-90"
                src="https://placehold.co/1200x500/0f172a/14b8a6?text=Dashboard+Financeiro"
                alt="Pre-visualizacao do dashboard"
              />
            </div>
          </div>
        </div>

        <div class="mt-14 grid grid-cols-1 md:grid-cols-3 gap-6">
          <div class="p-6 rounded-2xl bg-gray-900/70 border border-white/5 shadow-lg shadow-black/20">
            <p class="text-sm text-gray-400">Saldo previsto</p>
            <p class="text-3xl font-semibold text-white mt-2">EUR 2 480,00</p>
            <p class="text-teal-300 text-sm mt-2">+12% vs mes anterior</p>
          </div>
          <div class="p-6 rounded-2xl bg-gray-900/70 border border-white/5 shadow-lg shadow-black/20">
            <p class="text-sm text-gray-400">Categorias em destaque</p>
            <p class="text-3xl font-semibold text-white mt-2">05 categorias</p>
            <p class="text-gray-400 text-sm mt-2">Viagens, alimentacao, renda...</p>
          </div>
          <div class="p-6 rounded-2xl bg-gray-900/70 border border-white/5 shadow-lg shadow-black/20">
            <p class="text-sm text-gray-400">Alertas ativos</p>
            <p class="text-3xl font-semibold text-white mt-2">02 avisos</p>
            <p class="text-orange-300 text-sm mt-2">Budget a 80% em compras</p>
          </div>
        </div>
      </section>
    </main>

    <section id="features" class="py-16 bg-transparent">
      <div class="max-w-6xl mx-auto px-6 lg:px-10">
        <div class="text-center mb-12">
          <p class="text-teal-300 font-semibold uppercase tracking-wide text-sm">Funcionalidades</p>
          <h2 class="text-3xl sm:text-4xl font-bold text-white mt-3">Tudo o que precisa para gerir o seu dinheiro</h2>
          <p class="mt-4 text-gray-300 max-w-3xl mx-auto">
            O segredo para ganhar dinheiro é saber gerir e poupar-lo.
          </p>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <div class="group relative p-6 rounded-2xl bg-gray-900/70 border border-white/5 shadow-xl shadow-black/30 hover:border-teal-400/40 transition-colors duration-200">
            <div class="h-12 w-12 rounded-xl bg-teal-500/20 text-teal-300 flex items-center justify-center">
              <svg class="w-7 h-7" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M3 8h18M3 12h18M7 16h10" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold text-white mt-4">Controle de transações</h3>
            <p class="text-gray-300 mt-3">Adicione receitas, gastos e etiquetas para ver onde o seu dinheiro entra e sai.</p>
            <p class="absolute inset-x-6 bottom-6 text-sm text-teal-300 opacity-0 group-hover:opacity-100 transition-opacity">por ligação para a dashboard</p>
          </div>

          <div class="group relative p-6 rounded-2xl bg-gray-900/70 border border-white/5 shadow-xl shadow-black/30 hover:border-teal-400/40 transition-colors duration-200">
            <div class="h-12 w-12 rounded-xl bg-teal-500/20 text-teal-300 flex items-center justify-center">
              <svg class="w-7 h-7" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M11 3.055A9 9 0 1020.945 13H11z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M13 11h8.944" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold text-white mt-4">Gestão de orçamentos</h3>
            <p class="text-gray-300 mt-3">Defina limites por categoria e receba alertas antes de ultrapassar o planeado.</p>
            <p class="absolute inset-x-6 bottom-6 text-sm text-teal-300 opacity-0 group-hover:opacity-100 transition-opacity">Ligação direta com os alertas da DashboardView.</p>
          </div>

          <div class="group relative p-6 rounded-2xl bg-gray-900/70 border border-white/5 shadow-xl shadow-black/30 hover:border-teal-400/40 transition-colors duration-200">
            <div class="h-12 w-12 rounded-xl bg-teal-500/20 text-teal-300 flex items-center justify-center">
              <svg class="w-7 h-7" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M4 19h4V9H4zM10 19h4v-6h-4zM16 19h4V5h-4z" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold text-white mt-4">Relatórios visuais</h3>
            <p class="text-gray-300 mt-3">Veja tendencias mensais usando a mesma linguagem visual do dashboard.</p>
            <p class="absolute inset-x-6 bottom-6 text-sm text-teal-300 opacity-0 group-hover:opacity-100 transition-opacity">Colocar um grafico da que tenha na dashboard.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-16">
      <div class="max-w-6xl mx-auto px-6 lg:px-10 space-y-10">
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
          <div class="lg:col-span-2 p-8 rounded-3xl bg-gradient-to-br from-gray-900 via-gray-900/80 to-gray-800 border border-white/5 shadow-2xl shadow-black/30">
            <p class="text-sm uppercase tracking-wider text-teal-300 font-semibold">Passo a passo</p>
            <h3 class="text-2xl font-bold text-white mt-2">Como usar o gestor em 3 passos simples</h3>
            <div class="mt-8 space-y-6">
              <div class="flex gap-4">
                <div class="h-10 w-10 rounded-full bg-teal-500/20 text-teal-300 flex items-center justify-center font-semibold">1</div>
                <div>
                  <h4 class="text-lg font-semibold text-white">Registe as suas contas e categorias</h4>
                  <p class="text-gray-300 text-sm mt-1">Defina metas, objetivos e poupanças.</p>
                </div>
              </div>
              <div class="flex gap-4">
                <div class="h-10 w-10 rounded-full bg-teal-500/20 text-teal-300 flex items-center justify-center font-semibold">2</div>
                <div>
                  <h4 class="text-lg font-semibold text-white">Adicione transações rapidamente</h4>
                  <p class="text-gray-300 text-sm mt-1">Use etiquetas e notas curtas para deixar claro o contexto de cada movimento.</p>
                </div>
              </div>
              <div class="flex gap-4">
                <div class="h-10 w-10 rounded-full bg-teal-500/20 text-teal-300 flex items-center justify-center font-semibold">3</div>
                <div>
                  <h4 class="text-lg font-semibold text-white">Analise insights no dashboard</h4>
                  <p class="text-gray-300 text-sm mt-1">Compare meses, veja alertas e analise o seu gráfico mensal.</p>
                </div>
              </div>
            </div>
          </div>

          <div class="p-8 rounded-3xl bg-gray-900/80 border border-white/5 shadow-2xl shadow-black/40 flex flex-col gap-6">
            <div>
              <p class="text-sm text-gray-400">Objetivo mensal</p>
              <p class="text-4xl font-bold text-white mt-2">€ 1 200</p>
              <p class="text-sm text-teal-300 mt-1">Meta: poupar para emergencias</p>
            </div>
            <div>
              <p class="text-sm text-gray-400">Progresso</p>
              <div class="mt-3 bg-gray-800 rounded-full h-3 overflow-hidden">
                <div class="h-full bg-gradient-to-r from-teal-400 to-cyan-400 w-3/4"></div>
              </div>
              <p class="text-sm text-gray-400 mt-2">75% concluido - falta € 300</p>
            </div>
            <div class="p-4 rounded-2xl bg-teal-500/10 border border-teal-400/30">
              <p class="text-sm text-teal-200">Dica do dia</p>
              <p class="text-white font-semibold mt-1">por colocar.</p>
            </div>
          </div>
        </div>

        <div class="rounded-3xl border border-white/5 bg-gray-900/70 shadow-xl p-10 text-center space-y-6">
          <p class="text-sm uppercase tracking-widest text-teal-300 font-semibold">Pronto para testar?</p>
          <h3 class="text-3xl font-bold text-white">Conecte-se ao dashboard e veja os dados ganharem vida</h3>
          <p class="text-gray-300 max-w-3xl mx-auto">colocar algum texto .</p>
          <div class="flex flex-col sm:flex-row justify-center gap-4">
            <a href="/login" class="inline-flex items-center justify-center px-8 py-3 rounded-xl font-semibold bg-teal-500 text-gray-900 hover:bg-teal-400 transition-colors duration-200 shadow-lg shadow-teal-500/30">
              Aceder ao painel
            </a>
            <a href="#features" class="inline-flex items-center justify-center px-8 py-3 rounded-xl font-semibold border border-white/20 text-gray-100 hover:bg-white/5 transition-colors duration-200">
              Ver funcionalidades
            </a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
</script>
