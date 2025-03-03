<!--
Referência: https://www.mff.cuni.cz/en
-->

<template>
  <q-layout view="lhh lpR lff">
    <q-header elevated>

      <!-- Logo Principal -->
      <div v-show="$q.screen.gt.sm" class="q-pa-md flex flex-center bg-white">
        <q-img src="img/logo-nome-azul.png" width="300px" />
      </div>

      <q-toolbar class="justify-between">
        <!-- Ícone do menu em telas menores -->
        <q-btn v-if="$q.screen.lt.md" flat dense square icon="menu" @click="drawer = !drawer" />

        <div v-show="$q.screen.lt.md" class="q-pa-md full-width flex flex-center">
          <q-img src="img/logo-nome-branco.png" width="100px" />
        </div>

        <!-- Botões do menu (Somente em telas maiores) -->
        <div class="gt-sm row justify-center full-width q-gutter-x-md toolbar-container">
          <q-btn flat dense to="/" class="q-pa-sm q-ma-sm toolbar-nav">INÍCIO</q-btn>
          <q-btn flat dense to="/" class="q-pa-sm q-ma-sm toolbar-nav">EII</q-btn>
          <q-btn flat dense to="/" class="q-pa-sm q-ma-sm toolbar-nav">PROCESSO SELETIVO</q-btn>
          <q-btn flat dense to="/" class="q-pa-sm q-ma-sm toolbar-nav">NOTÍCIAS</q-btn>
          <q-btn flat dense to="/membros" class="q-pa-sm q-ma-sm toolbar-nav">MEMBROS</q-btn>
          <q-btn flat dense to="/" class="q-pa-sm q-ma-sm toolbar-nav">PROJETOS</q-btn>
          <q-btn flat dense to="/" class="q-pa-sm q-ma-sm toolbar-nav">PUBLICAÇÕES</q-btn>
        </div>
      </q-toolbar>

    </q-header>

    <!-- Drawer para telas menores -->
    <q-drawer v-model="drawer" side="left" overlay>
      <q-list>
        <q-item clickable v-close-popup to="/">
          <q-item-section>INÍCIO</q-item-section>
        </q-item>
        <q-item clickable v-close-popup to="/">
          <q-item-section>EII</q-item-section>
        </q-item>
        <q-item clickable v-close-popup to="/">
          <q-item-section>PROCESSO SELETIVO</q-item-section>
        </q-item>
        <q-item clickable v-close-popup to="/">
          <q-item-section>NOTÍCIAS</q-item-section>
        </q-item>
        <q-item clickable v-close-popup to="/membros">
          <q-item-section>MEMBROS</q-item-section>
        </q-item>
        <q-item clickable v-close-popup to="/">
          <q-item-section>PROJETOS</q-item-section>
        </q-item>
        <q-item clickable v-close-popup to="/">
          <q-item-section>PUBLICAÇÕES</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="bg-primary text-white q-pa-md">
      <q-toolbar class="column items-center">

        <!-- Ícones de redes sociais -->
        <div class="row justify-center q-mt-md q-gutter-sm">
          <q-btn flat dense round icon="ion-logo-instagram" class="text-white" href="https://www.instagram.com/instufs"
            target="_blank">
            <q-tooltip anchor="top middle" self="bottom middle">Instagram</q-tooltip>
          </q-btn>

          <q-btn flat dense round icon="ion-logo-linkedin" class="text-white"
            href="https://www.linkedin.com/company/instufs" target="_blank">
            <q-tooltip anchor="top middle" self="bottom middle">LinkedIn</q-tooltip>
          </q-btn>

          <q-btn flat dense round icon="ion-logo-youtube" class="text-white"
            href="https://www.youtube.com/@instrumentacaoeletronicauf1621/videos" target="_blank">
            <q-tooltip anchor="top middle" self="bottom middle">YouTube</q-tooltip>
          </q-btn>

          <q-btn flat dense round icon="ion-logo-github" class="text-white" href="https://github.com/instufs"
            target="_blank">
            <q-tooltip anchor="top middle" self="bottom middle">GitHub</q-tooltip>
          </q-btn>

          <q-btn flat dense round icon="img:img/dgp.png" class="text-white"
            href="http://dgp.cnpq.br/dgp/espelhogrupo/0152555842375554" target="_blank">
            <q-tooltip anchor="top middle" self="bottom middle">Grupo de Pesquisa</q-tooltip>
          </q-btn>
        </div>

        <!-- Texto de direitos autorais -->
        <div class="column items-center text-center q-mt-md">
          <div class="text-caption">
            &copy; 2014 - {{ new Date().getFullYear() }}
          </div>
          <div class="text-caption">
            Grupo de Pesquisa em Instrumentação Eletrônica
          </div>
          <div class="text-caption">
            Universidade Federal de Sergipe
          </div>
        </div>

      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script setup>
import { ref } from 'vue';

const drawer = ref(false);
</script>


<style scoped>
.toolbar-container {
  display: flex;
  align-items: center;
}

.toolbar-nav {
  color: white;
  font-weight: bold;
}

.separator {
  height: 24px; /* Tamanho da linha */
  background-color: rgba(255, 255, 255, 0.5); /* Cor da linha */
  width: 2px; /* Largura da linha */
}
</style>
