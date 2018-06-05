<template>
  <div>
    <md-empty-state></md-empty-state>
      <md-table-row slot="md-table-row" slot-scope="{ item }" :md-disabled="item.name.includes('Stave')" md-selectable="multiple" md-auto-select>
        <md-table-cell md-label="Email" md-sort-by="email">{{ reembolso.email }}</md-table-cell>
        <md-table-cell md-label="Reembolso" md-sort-by="Reembolso">{{ reembolso.reembolso }}</md-table-cell>
        <md-table-cell md-label="Status" md-sort-by="status">{{ reembolso.status }}</md-table-cell>
        <md-table-cell md-label="Valor" md-sort-by="valor">{{ reembolso.valor }}</md-table-cell>
        <md-table-cell md-label="Categoria" md-sort-by="categoria">{{ reembolso.categoria }}</md-table-cell>
        <md-table-cell md-label="User" md-sort-by="user">{{ reembolso.user }}</md-table-cell>
      </md-table-row>
  </div>
</template>

<script>
  export default {
    name: 'Reembolso',
    props: ['reembolso'],
    data: () => ({
      selected: [],

    }),
    methods: {
      onSelect (items) {
        this.selected = items
      },
      getAlternateLabel (count) {
        let plural = ''

        if (count > 1) {
          plural = 's'
        }

        return `${count} user${plural} selected`
      }
    }
  }
</script>

<style lang="scss" scoped>
  .md-table + .md-table {
    margin-top: 16px
  }
</style>
