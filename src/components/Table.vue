<template>
  <div id="table">
    <div id="navigation">
      <div class="first">Контрольная панель</div>
      <div class="first" v-for="index in 30" :key="index">Пример БК</div>
    </div>
    <div id="body">
      <div class="header">
        <div class="info" v-for="index in 10" :key="index">
          <div>132,5</div>
          <div>ТБ</div>
          <div>ТМ</div>
        </div>
      </div>
      <div id="data">
        <div class="row" v-for="index in 30" :key="index">
          <div class="cell"><span class="coff">1,54</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">1,54</span></div>
          <div class="cell"><span class="coff red">1,54</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff green">1,54</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">1,54</span></div>
          <div class="cell"><span class="coff">1,54</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">1,54</span></div>
          <div class="cell"><span class="coff red">1,54</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff green">1,54</span></div>
          <div class="cell"><span class="coff">-</span></div>
          <div class="cell"><span class="coff">1,54</span></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Table'
}
</script>

<style scoped lang="scss">
  #table {
    --cell-width: 150px;
    --first-width: 300px;
    padding-left: var(--padding);
    padding-right: var(--padding);
    padding-bottom: var(--padding);
    display: grid;
    grid-template-columns: var(--first-width) minmax(0, 1fr);

    #navigation {
      display: grid;
      grid-auto-rows: auto;
      grid-auto-flow: row;
      align-items: center;
      background-color: var(--table);
      border-top-left-radius: calc(var(--padding) / 2);
      transition: background-color var(--transition);
      .first {
        border-left: 3px solid var(--border-color);
        border-right: 2px solid var(--border-color);
        position: relative;
        &:nth-child(2n -1):before {
          content: ' ';
          position: absolute;
          left: 0;
          top: 0;
          right: 0;
          bottom: 0;
          background-color: var(--border-color);
          opacity: 0.5;
          z-index: 0;
        }
        &:first-child {
          display: flex;
          height: 90px;
          padding-top: 0;
          padding-bottom: 0;
          background-color: var(--border-color);
          align-items: center;
          border-top-left-radius: calc(var(--padding) / 2);
          &:before {
            display: none;
          }
        }
      }
    }
    #body {
      display: grid;
      max-width: 100%;
      overflow: scroll;
      grid-auto-flow: row;
      grid-auto-rows: auto;
      background-color: var(--table);
      transition: background-color var(--transition);
      #data {
        display: grid;
        grid-auto-flow: row;
        grid-auto-rows: auto;
      }
      .row {
        display: grid;
        grid-auto-flow: column;
        grid-auto-columns: calc(var(--cell-width) / 2);
        position: relative;
        align-items: center;
        &:nth-child(2n):before {
          content: ' ';
          position: absolute;
          left: 0;
          top: 0;
          right: 0;
          bottom: 0;
          background-color: var(--border-color);
          opacity: 0.5;
          z-index: 0;
        }
      }
    }
    .header {
      display: grid;
      grid-column: 1/3;
      grid-auto-columns: var(--cell-width);
      grid-auto-flow: column;
      background-color: var(--border-color);
      align-items: center;
      border-top-right-radius: calc(var(--padding) / 2);
      font-weight: 700;
    }
    .first {
      text-align: left;
      padding: calc(var(--padding) / 2);
    }
    .cell {
      text-align: center;
      padding: calc(var(--padding) / 2) 0;
      border-right: 2px solid var(--border-color);
      position: relative;
    }
    .info {
      display: grid;
      grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
      text-align: center;
      align-items: center;
      height: 90px;
      div {
        padding: calc(var(--padding) / 4);
        &:first-child {
          grid-column: 1/3;
          & + div, & + div + div {
            opacity: 0.5;
          }
        }
      }
    }
  }
  .coff {
    font-weight: 700;
    padding: 5px 10px;
    border-radius: 5px;
    transition: color var(--transition);
    &.red {
      background-color: #FF8D8D;
    }
    &.green {
      background-color: #85DA9D;
    }
  }
</style>
