<script setup lang="ts">
import type { GlobalThemeOverrides } from 'naive-ui'
import { darkTheme, NButton, NConfigProvider, NDivider, NInput } from 'naive-ui'
import { RouterLink } from 'vue-router'

const naiveThemeOverrides: GlobalThemeOverrides = {
  common: {
    borderRadius: '5px',
    primaryColor: '#f49a27',
    primaryColorHover: '#ffb454',
    primaryColorPressed: '#d77f14',
  },
  Input: {
    border: '1px solid var(--color-garage-border)',
    borderHover: '1px solid var(--color-garage-orange)',
    borderFocus: '1px solid var(--color-garage-orange)',
    boxShadowFocus: '0 0 0 2px rgba(244, 154, 39, 0.18)',
    color: 'var(--color-garage-input)',
    colorFocus: 'var(--color-garage-input)',
    textColor: '#f8fafc',
    placeholderColor: 'var(--color-garage-muted)',
    heightLarge: '56px',
    fontSizeLarge: '16px',
    paddingLarge: '0 20px',
  },
  Button: {
    color: 'transparent',
    colorHover: '#151923',
    colorPressed: '#151923',
    colorFocus: '#151923',
    colorPrimary: 'var(--color-garage-orange)',
    colorHoverPrimary: 'var(--color-garage-orange-soft)',
    colorPressedPrimary: 'var(--color-garage-orange-deep)',
    colorFocusPrimary: 'var(--color-garage-orange)',
    textColor: '#f8fafc',
    textColorHover: '#f8fafc',
    textColorPressed: '#f8fafc',
    textColorFocus: '#f8fafc',
    textColorPrimary: '#0e1014',
    textColorHoverPrimary: '#0e1014',
    textColorPressedPrimary: '#0e1014',
    textColorFocusPrimary: '#0e1014',
    border: '1px solid var(--color-garage-border)',
    borderHover: '1px solid var(--color-garage-border-soft)',
    borderPressed: '1px solid var(--color-garage-border-soft)',
    borderFocus: '1px solid var(--color-garage-border-soft)',
    borderPrimary: '1px solid var(--color-garage-orange)',
    borderHoverPrimary: '1px solid var(--color-garage-orange-soft)',
    borderPressedPrimary: '1px solid var(--color-garage-orange-deep)',
    borderFocusPrimary: '1px solid var(--color-garage-orange)',
    heightLarge: '54px',
    fontSizeLarge: '14px',
    fontWeight: '500',
    fontWeightStrong: '600',
  },
  Divider: {
    color: 'var(--color-garage-border)',
    textColor: 'var(--color-garage-muted)',
    fontWeight: '400',
  },
}
</script>

<template>
  <NConfigProvider :theme="darkTheme" :theme-overrides="naiveThemeOverrides">
    <main class="grid min-h-screen grid-cols-1 bg-garage-900 text-slate-50 lg:grid-cols-5">
      <section
        class="garage-stripes relative flex min-h-96 flex-col justify-between overflow-hidden border border-garage-border p-8 lg:col-span-3 lg:min-h-screen lg:border-r-0 lg:p-14 xl:p-16"
        aria-label="Presentation Auto Guessr"
      >
        <RouterLink
          class="w-fit font-display text-3xl font-bold tracking-widest text-white uppercase"
          to="/"
        >
          AUTOGUESSR
        </RouterLink>

        <p class="hidden self-center text-center font-mono text-base leading-8 text-slate-500 md:block">
          photo - voiture de profil sous éclairage garage,<br />
          halo chaud, sol béton, fond noir
        </p>

        <div class="max-w-4xl">
          <p class="text-xs font-semibold tracking-widest text-garage-orange uppercase">
            Quiz du jour disponible
          </p>
          <h1
            class="mt-2 mb-3 font-display text-4xl leading-none font-bold tracking-wide text-white uppercase lg:text-5xl"
          >
            5 voitures t'attendent au garage
          </h1>
          <p class="text-sm text-slate-400">
            Ta série en cours : x4 - connecte-toi avant minuit pour la garder.
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

          <NButton
            type="primary"
            attr-type="submit"
            block
            size="large"
            class="mt-8 tracking-widest uppercase"
          >
            Se connecter
          </NButton>

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
  </NConfigProvider>
</template>
