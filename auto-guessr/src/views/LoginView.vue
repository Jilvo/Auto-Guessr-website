<script setup lang="ts">
import { NButton, NDivider, NInput } from 'naive-ui'
import { RouterLink } from 'vue-router'
</script>

<template>
  <main class="grid min-h-screen grid-cols-1 bg-garage-900 text-slate-50 lg:grid-cols-5">
    <section
      class="relative isolate flex min-h-96 flex-col justify-between overflow-hidden border border-garage-border p-8 lg:col-span-3 lg:min-h-screen lg:border-r-0 lg:p-14 xl:p-16"
      aria-label="Presentation Auto Guessr"
    >
      <img
        src="@/assets/images/lamborghini-aventador.jpg"
        alt="Garage"
        class="absolute inset-0 z-0 h-full w-full object-cover object-center opacity-80"
      />
      <div class="absolute inset-0 z-0 bg-garage-900/60"></div>

      <RouterLink
        class="relative z-10 w-fit font-display text-3xl font-bold tracking-widest text-white uppercase"
        to="/"
      >
        AUTOGUESSR
      </RouterLink>

      <div class="relative z-10 max-w-4xl">
        <p class="text-xs font-semibold tracking-widest text-garage-orange uppercase">
          Quiz du jour disponible
        </p>
        <h1
          class="mt-2 mb-3 font-display text-4xl leading-none font-bold tracking-wide text-white uppercase lg:text-5xl"
        >
          5 voitures t'attendent au garage
        </h1>
        <p class="text-sm text-slate-400">
          Tu as une série en cours ? - connecte-toi avant minuit pour la garder.
        </p>
      </div>
    </section>

    <section
      class="grid min-h-96 place-items-center border border-garage-border bg-garage-800 px-6 py-10 lg:col-span-2 lg:min-h-screen lg:px-0"
      aria-label="Connexion"
    >
      <form class="w-full max-w-xl lg:w-3/4" @submit.prevent>
        <p class="text-xs font-semibold tracking-widest text-slate-400 uppercase">
          Connexion
        </p>
        <h2
          class="mt-2 mb-10 font-display text-4xl leading-none font-bold tracking-wide text-white uppercase xl:text-5xl"
        >
          Bon retour au garage
        </h2>

        <label
          class="mb-2 block text-xs font-semibold tracking-widest text-slate-400 uppercase"
          for="email"
        >
          Email
        </label>
        <NInput
          id="email"
          type="text"
          size="large"
          placeholder="pilote@example.fr"
          autocomplete="email"
        />

        <div class="mt-5 mb-2.5 flex items-center justify-between gap-4">
          <label
            class="text-xs font-semibold tracking-widest text-slate-400 uppercase"
            for="password"
          >
            Mot de passe
          </label>
          <a class="text-sm font-medium text-garage-orange" href="#">Oublié ?</a>
        </div>
        <NInput
          id="password"
          type="password"
          size="large"
          placeholder="********"
          autocomplete="current-password"
          show-password-on="mousedown"
        />
        <div class="mt-8">

          <NButton
          type="primary"
          attr-type="submit"
          block
          size="large"
          class="mt-8 tracking-widest uppercase"
          >
          Se connecter
        </NButton>
      </div>

        <NDivider>ou</NDivider>

        <div class="grid grid-cols-2 gap-4">
          <NButton block size="large">Google</NButton>
          <NButton block size="large">Apple</NButton>
        </div>

        <p class="mt-8 text-sm text-slate-400">
          Pas encore de garage ?
          <RouterLink class="font-medium text-garage-orange" to="/signup">
            Créer un compte
          </RouterLink>
        </p>
      </form>
    </section>
  </main>
</template>
