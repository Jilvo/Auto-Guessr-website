<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { NButton, NCard, NGi, NGrid, NSpace } from 'naive-ui'
</script>

<template>
  <div class="landing-page">
    <header class="site-header">
      <RouterLink class="brand" to="/">Auto Guessr</RouterLink>

      <nav class="navigation" aria-label="Navigation principale">
        <RouterLink to="/login">
          <n-button type="primary" round>Connexion</n-button>
        </RouterLink>
      </nav>
    </header>

    <main class="hero">
      <section class="hero-content">
        <p class="eyebrow">Jeu de geographie</p>
        <h1>Devine l'endroit, marque des points, grimpe au classement.</h1>
        <p class="description">
          Auto Guessr te propose des lieux a identifier le plus vite possible.
          Observe les indices, place ta reponse, puis compare ton score.
        </p>

        <n-space class="hero-actions" :size="12">
          <RouterLink to="/login">
            <n-button type="error" size="large" round>Commencer</n-button>
          </RouterLink>

          <a href="#features">
            <n-button size="large" round>Voir le principe</n-button>
          </a>
        </n-space>
      </section>

      <section class="preview-panel" aria-label="Apercu de partie">
        <n-card embedded :bordered="false" content-style="padding: 0">
          <div class="map-preview">
            <span class="pin"></span>
          </div>
        </n-card>

        <n-card size="small" class="score-preview">
          <span>Score actuel</span>
          <strong>1 250 pts</strong>
        </n-card>
      </section>
    </main>

    <n-grid
      id="features"
      class="features"
      aria-label="Fonctionnalites"
      :cols="3"
      :x-gap="16"
      :y-gap="16"
      responsive="screen"
      item-responsive
    >
      <n-gi span="3 m:1">
        <n-card title="Observe" size="small">
          Analyse les indices visuels avant de placer ta reponse.
        </n-card>
      </n-gi>

      <n-gi span="3 m:1">
        <n-card title="Devine" size="small">
          Choisis une position et valide ton intuition.
        </n-card>
      </n-gi>

      <n-gi span="3 m:1">
        <n-card title="Progresse" size="small">
          Compare tes scores et essaie de faire mieux a chaque partie.
        </n-card>
      </n-gi>
    </n-grid>
  </div>
</template>

<style scoped>
.landing-page {
  min-height: 100vh;
  color: #18202a;
  background:
    radial-gradient(circle at top left, rgba(50, 130, 184, 0.18), transparent 34rem),
    linear-gradient(135deg, #f7fbf8 0%, #eef5f1 46%, #f4f0e8 100%);
}

.site-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1120px;
  margin: 0 auto;
  padding: 1.25rem;
}

.brand {
  color: inherit;
  font-size: 1.15rem;
  font-weight: 800;
}

.navigation {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.hero {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(18rem, 26rem);
  gap: 3rem;
  align-items: center;
  max-width: 1120px;
  margin: 0 auto;
  padding: 5rem 1.25rem 4rem;
}

.hero-content {
  max-width: 42rem;
}

.eyebrow {
  margin: 0 0 1rem;
  color: #1e6f5c;
  font-size: 0.8rem;
  font-weight: 800;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

h1 {
  margin: 0;
  font-size: clamp(2.5rem, 7vw, 5.5rem);
  line-height: 0.98;
}

.description {
  max-width: 35rem;
  margin: 1.5rem 0 0;
  color: #4a5864;
  font-size: 1.1rem;
  line-height: 1.7;
}

.hero-actions {
  margin-top: 2rem;
}

.preview-panel {
  display: grid;
  gap: 1rem;
}

.map-preview {
  position: relative;
  min-height: 22rem;
  overflow: hidden;
  border-radius: 0.5rem;
  background:
    linear-gradient(90deg, rgba(255, 255, 255, 0.35) 1px, transparent 1px),
    linear-gradient(rgba(255, 255, 255, 0.35) 1px, transparent 1px),
    linear-gradient(135deg, #9fc8a9, #6aa6b4 52%, #d7c48e);
  background-size: 3rem 3rem, 3rem 3rem, auto;
  box-shadow: 0 1.5rem 4rem rgba(31, 59, 52, 0.16);
}

.pin {
  position: absolute;
  top: 46%;
  left: 54%;
  width: 1.4rem;
  height: 1.4rem;
  border: 0.25rem solid #ffffff;
  border-radius: 50%;
  background: #d93939;
  box-shadow: 0 0.75rem 1.5rem rgba(91, 24, 24, 0.35);
}

.score-preview {
  background: rgba(255, 255, 255, 0.78);
}

.score-preview :deep(.n-card__content) {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}

.score-preview span {
  color: #65717c;
}

.score-preview strong {
  font-size: 1.35rem;
}

.features {
  max-width: 1120px;
  margin: 0 auto;
  padding: 0 1.25rem 4rem;
}

@media (max-width: 760px) {
  .hero {
    grid-template-columns: 1fr;
    padding-top: 3rem;
  }

  .map-preview {
    min-height: 16rem;
  }
}
</style>
