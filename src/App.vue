<template>
  <input class="hide" id="theme-control" type="checkbox">
  <div id="template">
    <div id="grid">
      <Header />
      <Filter />
      <Table />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Filter from './components/Filter.vue'
import Table from './components/Table.vue'

export default {
  name: 'App',
  components: {
    Header,
    Filter,
    Table
  }
}
</script>

<style lang="scss">
  @import './styles/index.scss';

  #grid {
    display: grid;
    grid-auto-flow: row;
    grid-gap: var(--padding);
  }
</style>
