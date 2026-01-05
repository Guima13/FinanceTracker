<script setup>
import { ref } from 'vue'; // Adicionado para variáveis reativas

const etapas = [
  { titulo: 'Defina um objetivo principal', descricao: 'Ex: poupar para emergência ou viagem.' },
  { titulo: 'Escolha categorias prioritárias', descricao: 'Transporte, renda, investimentos etc.' },
  { titulo: 'Configure alertas mensais', descricao: 'Receba aviso quando atingir 80% do limite.' },
];

// --- Estado para os inputs do formulário ---
const formData = ref({
  name: '',
  email: '',
  password: '',
  terms: false,
});
// ------------------------------------------------

// --- Função para lidar com o Registro (Simulação POST) ---
async function handleRegister() {
  // 1. Validação básica dos campos obrigatórios
  if (!formData.value.name || !formData.value.email || !formData.value.password || !formData.value.terms) {
    alert('Por favor, preencha todos os campos e aceite os termos.');
    return;
  }

  // 2. Objeto a enviar ao Mock Server. Mapeia 'name' para 'username' no db.json
  const novoUtilizador = {
    username: formData.value.name,
    email: formData.value.email,
    password: formData.value.password, // Atenção: não seguro em produção
  };

  try {
    // CORRIGIDO: URL AGORA APONTA PARA A PORTA 4000
    const response = await fetch('http://localhost:4000/users', { 
      method: 'POST', // Usa o método HTTP POST para criar o registo
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(novoUtilizador),
    });

    if (response.ok) {
      // Registo bem-sucedido (o JSON Server adiciona o utilizador ao db.json)
      await response.json(); 
      alert(`✅ Registro simulado para ${novoUtilizador.username} bem-sucedido! Pode fazer login.`);
      
      // Simular redirecionamento para a página de login
      // window.location.href = '/login'; 
      
    } else {
      alert('❌ Erro no registro. Verifique a consola ou o JSON Server.');
    }
  } catch (error) {
    console.error('Erro de conexão com o Mock Server:', error);
    alert('Falha ao comunicar com o servidor simulado.');
  }
}
// -------------------------------------------------------------
</script>

<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-950 via-gray-900 to-gray-950 text-gray-100">
    <div class="absolute inset-0 opacity-30 pointer-events-none">
      <div class="w-72 h-72 bg-teal-500/25 blur-3xl rounded-full absolute -top-16 -left-10"></div>
      <div class="w-96 h-96 bg-cyan-400/20 blur-3xl rounded-full absolute top-20 right-0"></div>
    </div>

    <div class="relative max-w-6xl mx-auto px-6 lg:px-10 py-16 flex flex-col gap-10 lg:flex-row">
      <section class="w-full lg:w-[460px] rounded-3xl bg-gray-900/80 border border-white/10 p-8 shadow-2xl space-y-8">
        <div class="text-center space-y-2">
          <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Criar conta</p>
          <h1 class="text-3xl font-bold text-white">Comece o seu painel financeiro</h1>
          <p class="text-gray-300 text-sm">
            Registe-se para sincronizar gastos, metas e relatórios.
            Obtenha controlo total das suas finanças num só lugar.
          </p>
        </div>

        <form class="space-y-5" @submit.prevent="handleRegister">
          <div class="space-y-2">
            <label for="name" class="text-sm font-medium text-gray-300">Nome completo</label>
            <input
              id="name"
              type="text"
              v-model="formData.name" class="w-full rounded-2xl bg-gray-950/60 border border-white/10 px-4 py-3 text-sm text-gray-100 placeholder:text-gray-500 focus:border-teal-400 focus:ring-2 focus:ring-teal-500/40 outline-none"
              placeholder="Ex: Ana Martins"
            />
          </div>

          <div class="space-y-2">
            <label for="email" class="text-sm font-medium text-gray-300">Email</label>
            <input
              id="email"
              type="email"
              v-model="formData.email" class="w-full rounded-2xl bg-gray-950/60 border border-white/10 px-4 py-3 text-sm text-gray-100 placeholder:text-gray-500 focus:border-teal-400 focus:ring-2 focus:ring-teal-500/40 outline-none"
              placeholder="voce@email.com"
            />
          </div>

          <div class="space-y-2">
            <label for="password" class="text-sm font-medium text-gray-300">Senha</label>
            <input
              id="password"
              type="password"
              v-model="formData.password" class="w-full rounded-2xl bg-gray-950/60 border border-white/10 px-4 py-3 text-sm text-gray-100 placeholder:text-gray-500 focus:border-teal-400 focus:ring-2 focus:ring-teal-500/40 outline-none"
              placeholder="••••••••"
            />
          </div>

          <div class="flex items-center gap-2 text-sm text-gray-400">
            <input id="terms" type="checkbox" v-model="formData.terms" class="rounded bg-gray-800 border-gray-600 text-teal-400 focus:ring-teal-500" />
            <label for="terms">Aceito os termos e notificações do sistema.</label>
          </div>

          <button
            type="submit"
            class="w-full rounded-2xl bg-teal-500 py-3 text-sm font-semibold text-gray-900 shadow-lg shadow-teal-500/30 hover:bg-teal-400 transition"
          >
            Criar conta
          </button>
        </form>

        <p class="text-center text-sm text-gray-400">
          Já tem acesso?
          <a href="/login" class="text-teal-300 font-semibold hover:text-teal-200">Entrar</a>
        </p>
      </section>

      <section class="flex-1 rounded-3xl bg-gray-900/70 border border-white/10 p-8 shadow-2xl space-y-8">
        <div>
          <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Comece rápido</p>
          <h2 class="text-2xl font-bold text-white mt-2">3 passos para configurar o seu painel</h2>
          <p class="text-gray-300 mt-3">
            Assim que se registar, siga estes passos para aproveitar ao máximo a plataforma.
          </p>
        </div>

        <ul class="space-y-4">
          <li
            v-for="(etapa, index) in etapas"
            :key="etapa.titulo"
            class="flex items-start gap-4 rounded-2xl bg-gray-800/60 border border-white/5 p-4"
          >
            <span class="h-10 w-10 rounded-full bg-teal-500/20 text-teal-200 flex items-center justify-center font-semibold">
              {{ index + 1 }}
            </span>
            <div>
              <p class="text-white font-semibold">{{ etapa.titulo }}</p>
              <p class="text-sm text-gray-400 mt-1">{{ etapa.descricao }}</p>
            </div>
          </li>
        </ul>

        <div class="rounded-2xl bg-gray-800/60 border border-white/5 p-6 space-y-4">
          <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Em destaque</p>
          <h3 class="text-xl font-bold text-white">Dashboard Interativa</h3>
          <p class="text-gray-300">
            Faça proveito da nossa dashboard para obter uma visão clara dos seus gastos mensais.
          </p>
          <button class="inline-flex items-center gap-2 text-sm font-semibold text-teal-300 hover:text-teal-200">
            Utilizar modelo →
          </button>
        </div>
      </section>
    </div>
  </div>
</template>