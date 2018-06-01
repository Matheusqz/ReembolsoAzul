<template>
  <div id='App'>
    <md-toolbar class="md-primary">
      <md-button class="md-icon-button" @click="showNavigation = true">
        <md-icon>menu</md-icon>
      </md-button>
      <span class="md-title">ReembolsoAzul</span>
    </md-toolbar>

    <md-drawer :md-active.sync="showNavigation">
      <md-toolbar class="md-transparent" md-elevation="0">
        <span class="md-title">Reembolso ContaAzul</span>
      </md-toolbar>

      <md-list>
        <md-list-item>
          <router-link :to="{ name: 'Reembolsos', params: {} }">
            <md-icon>home</md-icon>Histórico e Solicitações
          </router-link>
        </md-list-item>

        <md-list-item>
          <router-link :to="{ name: 'Gastos', params: {} }">
            <md-icon>dashboard</md-icon>Dashboard de Gatos
          </router-link>
        </md-list-item>

        <md-list-item>
          <router-link :to="{ name: 'Perfil', params: {} }">
            <md-icon>perm_identity</md-icon>Perfil
          </router-link>
        </md-list-item>

        <md-list-item>
          <router-link :to="{ name: 'Home', params: {} }">
            <md-icon>input</md-icon>Sair
          </router-link>
        </md-list-item>
      </md-list>
    </md-drawer>

    <md-content>
      <router-view>
    </router-view>
    </md-content>
  </div>
</template>

<script>
  export default {
    name: 'App',
    data: () => ({
      showNavigation: false
    })
  }
</script>

<style lang="scss" scoped>
  .page-container {
    overflow: hidden;
    position: relative;
    border: 1px solid rgba(#000, .12);
  }

  .md-content {
    padding: 16px;
  }
</style>
