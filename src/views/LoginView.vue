<script setup>
const tips = [
  'Organize as suas contas numa unica linha do tempo.',
  'Defina alertas antes de atingir o limite do orçamento.',
  'Use etiquetas para encontrar gastos rapidamente.',
];
</script>

<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-950 via-gray-900 to-gray-950 text-gray-100">
    <div class="absolute inset-0 opacity-30 pointer-events-none">
      <div class="w-72 h-72 bg-teal-500/30 blur-3xl rounded-full absolute -top-16 -left-10"></div>
      <div class="w-96 h-96 bg-cyan-400/20 blur-3xl rounded-full absolute top-32 right-0"></div>
    </div>

    <div class="relative max-w-6xl mx-auto px-6 lg:px-10 py-16 flex flex-col gap-10 lg:flex-row">
      <section class="flex-1 rounded-3xl bg-gray-900/70 border border-white/10 p-8 shadow-2xl space-y-6">
        <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Bem-vindo de volta</p>
        <h1 class="text-3xl lg:text-4xl font-bold text-white">
          Entre para continuar a gerir as suas finanças inteligentes
        </h1>
        <p class="text-gray-300">
          O painel ajuda você a acompanhar gastos, metas e projeções em tempo real.
        </p>
        <ul class="space-y-4">
          <li
            v-for="(tip, index) in tips"
            :key="tip"
            class="flex items-start gap-3 rounded-2xl bg-gray-800/70 border border-white/5 p-4"
          >
            <span class="h-8 w-8 rounded-full bg-teal-500/20 text-teal-200 flex items-center justify-center font-semibold">
              {{ index + 1 }}
            </span>
            <p class="text-sm text-gray-200">{{ tip }}</p>
          </li>
        </ul>
      </section>

      <section class="w-full lg:w-[420px]">
        <div class="rounded-3xl bg-gray-900/80 border border-white/10 p-8 shadow-2xl space-y-8 backdrop-blur">
          <div class="text-center space-y-2">
            <p class="text-sm uppercase tracking-wide text-teal-300 font-semibold">Aceder</p>
            <h2 class="text-2xl font-bold text-white">Inicie sessão</h2>
            <p class="text-sm text-gray-400">Utilize o e-mail registado para continuar.</p>
          </div>

          <form class="space-y-6">
            <div class="space-y-2">
              <label for="email" class="text-sm font-medium text-gray-300">Email</label>
              <input
                id="email"
                type="email"
                class="w-full rounded-2xl bg-gray-950/60 border border-white/10 px-4 py-3 text-sm text-gray-100 placeholder:text-gray-500 focus:border-teal-400 focus:ring-2 focus:ring-teal-500/40 outline-none"
                placeholder="voce@email.com"
              />
            </div>

            <div class="space-y-2">
              <div class="flex items-center justify-between text-sm">
                <label for="password" class="font-medium text-gray-300">Senha</label>
                <a href="#" class="text-teal-300 hover:text-teal-200">Esqueci-me?</a>
              </div>
              <input
                id="password"
                type="password"
                class="w-full rounded-2xl bg-gray-950/60 border border-white/10 px-4 py-3 text-sm text-gray-100 placeholder:text-gray-500 focus:border-teal-400 focus:ring-2 focus:ring-teal-500/40 outline-none"
                placeholder="••••••••"
              />
            </div>

            <div class="flex items-center gap-2 text-sm text-gray-400">
              <input id="remember" type="checkbox" class="rounded bg-gray-800 border-gray-600 text-teal-400 focus:ring-teal-500" />
              <label for="remember">Manter sessão iniciada</label>
            </div>

            <button
              type="submit"
              class="w-full rounded-2xl bg-teal-500 py-3 text-sm font-semibold text-gray-900 shadow-lg shadow-teal-500/30 hover:bg-teal-400 transition"
            >
              Entrar
            </button>
          </form>

          <p class="text-center text-sm text-gray-400">
            Ainda não possui conta?
            <a href="/register" class="text-teal-300 font-semibold hover:text-teal-200">Criar conta</a>
          </p>
        </div>
      </section>
    </div>
  </div>
</template>