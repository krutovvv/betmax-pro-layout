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

  #template {
    font-family: 'Gilroy', sans-serif;
    font-weight: 400;
    background-color: var(--background-color);
    color: var(--color);
    transition: background-color var(--transition);
    height: calc(100vh - var(--padding));
    padding-bottom: var(--padding);
  }
  #grid {
    display: grid;
    grid-auto-flow: row;
    grid-gap: var(--padding);
    grid-template-rows: auto auto minmax(0, 1fr);
    height: calc(100vh - var(--padding));
  }
</style>
