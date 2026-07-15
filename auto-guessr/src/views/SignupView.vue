<script setup lang="ts">
import { NButton, NDivider, NInput, NCard } from 'naive-ui'
import { RouterLink } from 'vue-router'
</script>

<template>
    <main class="relative grid min-h-screen grid-cols-1 bg-garage-900 text-slate-50 lg:grid-cols-5">
        <RouterLink
            class="absolute top-8 left-8 z-20 w-fit font-display text-3xl font-bold tracking-widest text-white uppercase lg:top-14 lg:left-14"
            to="/">
            AUTOGUESSR
        </RouterLink>

        <section
            class="grid min-h-96 place-items-center border border-garage-border bg-garage-800 px-6 py-10 lg:col-span-2 lg:min-h-screen lg:px-0"
            aria-label="Création de compte">
            <form class="w-full max-w-xl lg:w-3/4" @submit.prevent>
                <p class="text-xs font-semibold tracking-widest text-slate-400 uppercase">
                    Création de compte
                </p>
                <h2
                    class="mt-2 mb-10 font-display text-4xl leading-none font-bold tracking-wide text-white uppercase xl:text-5xl">
                    Ouvre ton garage
                </h2>
                <div class="mt-5 mb-2.5">

                    <label class="mb-2 block text-xs font-semibold tracking-widest text-slate-400 uppercase"
                        for="pseudo">
                        Pseudo
                    </label>
                    <NInput id="pseudo" type="text" size="large" placeholder="John Doe" autocomplete="pseudo" />
                </div>
                <div class="mt-5 mb-2.5">
                    <label class="mb-2 block text-xs font-semibold tracking-widest text-slate-400 uppercase"
                        for="email">
                        email
                    </label>

                    <NInput id="email" type="text" size="large" placeholder="john.doe@example.com"
                        autocomplete="email" />

                </div>
                <div class="mt-5 mb-2.5 flex items-center justify-between gap-4">
                    <label class="text-xs font-semibold tracking-widest text-slate-400 uppercase" for="password">
                        Mot de passe
                    </label>
                </div>
                <NInput id="password" type="password" size="large" placeholder="********"
                    autocomplete="current-password" show-password-on="mousedown" />
                <div class="mt-8">

                    <NButton type="primary" attr-type="submit" block size="large"
                        class="mt-8 tracking-widest uppercase">
                        Créer mon compte
                    </NButton>
                </div>

                <NDivider>ou</NDivider>

                <div class="grid grid-cols-2 gap-4">
                    <NButton block size="large">Google</NButton>
                    <NButton block size="large">Apple</NButton>
                </div>

                <p class="mt-8 text-sm text-slate-400">
                    Déjà membre ?
                    <RouterLink class="font-medium text-garage-orange" to="/login">
                        Se connecter
                    </RouterLink>
                </p>
            </form>
        </section>

        <section
            class="relative isolate flex min-h-96 flex-col overflow-hidden border border-garage-border p-8 lg:col-span-3 lg:min-h-screen lg:border-r-0 lg:p-14 xl:p-16"
            aria-label="Presentation Auto Guessr">
            <img src="@/assets/images/whte-voiture-garee_417767-560.avif" alt="Garage"
                class="absolute inset-0 z-0 h-full w-full object-cover object-center opacity-80" />
            <div class="absolute inset-0 z-0 bg-garage-900/60"></div>

            <div class="relative z-10 mt-auto max-w-4xl">
                <p class="mb-6 text-xs font-semibold tracking-widest text-garage-orange uppercase">
                    Ce qui t'attend
                </p>
                <div class="flex gap-10">
                <n-card title="20 voitures">
                    <p class="text-sm text-slate-400">
                        Découvre nos dernières voitures disponibles !
                    </p>
                </n-card>
                <n-card title="20 badges">
                    <p class="text-sm text-slate-400">
                        Plaques de collection : pays, décennies, marques et modèles, collectionne-les toutes !
                    </p>
                </n-card>
                <n-card title="Série & XP">
                    <p class="text-sm text-slate-400">
                        Progression sauvegardée, quiz du jour et classements entre amis !
                    </p>
                </n-card>
                <!-- <h1
                    class="mt-2 mb-3 font-display text-4xl leading-none font-bold tracking-wide text-white uppercase lg:text-5xl">
                    5 voitures t'attendent au garage
                </h1>
                <p class="text-sm text-slate-400">
                    Tu as une série en cours ? - connecte-toi avant minuit pour la garder.
                </p> -->
                </div>
            </div>
        </section>

    </main>
</template>
