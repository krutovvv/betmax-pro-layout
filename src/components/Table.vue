<template>
  <input id="header-big" type="checkbox" class="hide">
  <div id="table">
    <div class="row header">
      <div class="control">
        <div class="control-type">
          <div class="title">2 : 0</div>
          <div class="caption">(2:0; 5:0)</div>
        </div>
        <label for="header-big" class="control-toggle button">
          <svg width="9" height="14" viewBox="0 0 9 14" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M7.52222 12.9409L1.32114 6.98674L7.52222 1.03256" stroke="#FCFCFC" stroke-width="1.78111" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </label>
      </div>
      <div class="info" v-for="index in 10" :key="index">
        <div><span>132,5</span></div>
        <div><span>ТБ</span></div>
        <div><span>ТМ</span></div>
      </div>
    </div>
    <div class="row" v-for="index in 30" :key="index">
      <div class="cell">
        <div class="service">
          <div class="logo"><img src="../assets/services/service-1.png" alt="service"></div>
          <div class="data">
            <div>
              <div class="title">СШОР-121 Московского района U21 years - Ядро 321 Санкт-Петербург U21 years</div>
              <div class="stats">7:0 (2:0; 5:0)</div>
            </div>
          </div>
        </div>
      </div>
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
</template>

<script>
export default {
  name: 'Table'
}
</script>

<style scoped lang="scss">
  #header-big:checked + #table {
    --first-size: 5;
    .control svg {
      transform: rotate(0deg);
    }
    .service {
      grid-template-columns: 150px minmax(0, 1fr);
      .data {
        display: grid;
      }
    }
  }
  #table {
    --cell-width: 120px;
    --first-size: 2;

    margin-left: var(--padding);
    margin-right: var(--padding);

    display: grid;
    grid-auto-flow: row;
    overflow: scroll;
    border-top-left-radius: calc(var(--padding) / 2);
    position: relative;

    &::-webkit-scrollbar {
      width: 2px;
      height: 2px;
    }
    &::-webkit-scrollbar-thumb  {
      background-color: var(--scroll);
      border-radius: 10px;
      opacity: 0.5;
    }
    &::-webkit-scrollbar-button, &::-webkit-scrollbar-track, &::-webkit-scrollbar-track-piece, &::-webkit-scrollbar-corner, &::-webkit-resizer {
      display: none;
      width: 0;
      height: 0;
    }

    &:after {
      content: '';
      position: absolute;
      right: 0;
      top: 0;
      bottom: 0;
      width: var(--padding);
      background: linear-gradient(270deg, #24272F 55.21%, rgba(36, 39, 47, 0) 97.92%);;
    }
    .control {
      display: grid;
      align-items: center;
      position: sticky;
      grid-template-columns: auto minmax(0, 1fr);
      grid-gap: calc(var(--padding) / 2);
      top: 0;
      left: 0;
      grid-column: 1 / calc(var(--first-size) + 1);
      color: var(--color);
      z-index: 3;
      background-color: var(--table);
      padding: calc(var(--padding) / 2);
      border-right: 2px solid var(--border-color);
      border-top-left-radius: calc(var(--padding) / 2);
      transition: background-color var(--transition), color var(--transition), border-color var(--transition);
      .control-type {
        display: grid;
        grid-auto-flow: row;
        grid-gap: calc(var(--padding) / 4);
        background-color: #ffffff;
        padding: calc(var(--padding) / 4) var(--padding);
        text-align: center;
        border-radius: calc(var(--padding) / 2);
        transition: background-color var(--transition);
        .title {
          color: var(--scroll);
          font-size: 24px;
          font-weight: 900;
          transition: color var(--transition)
        }
        .caption {
          color: #000000;
          font-size: 13px;
        }
      }
      .control-toggle {
        width: var(--padding);
        height: var(--padding);
        display: inline-flex;
        font-size: 0;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        svg {
          transform: rotate(180deg);
          transition: transform var(--transition);
        }
        path {
          stroke: var(--button-color);
          transition: stroke var(--transition);
        }
        &:hover {
          path {
            stroke: var(--button-color-hover);
            transition: stroke var(--transition);
          }
        }
      }
    }
    .row {
      display: grid;
      grid-auto-flow: column;
      grid-auto-columns: calc(var(--cell-width) / 2);
      &.header {
        grid-auto-columns: var(--cell-width);
        border-top-left-radius: calc(var(--padding) / 2);
        border-top-right-radius: calc(var(--padding) / 2);
      }
      &:first-child {
        position: sticky;
        top: 0;
        z-index: 3;
      }
      &:nth-child(2n) .cell:before {
        content: '';
        background-color: var(--odd);
        position: absolute;
        left: 0;
        top: 0;
        right: 0;
        bottom: 0;
        opacity: 0.5;
        z-index: -1;
        transition: background-color var(--transition);
      }
      &:nth-child(2n - 1) .cell:before {
        content: '';
        background-color: var(--even);
        position: absolute;
        left: 0;
        top: 0;
        right: 0;
        bottom: 0;
        z-index: -1;
        transition: background-color var(--transition);
      }
    }
    .cell {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: calc(var(--padding) / 2) 0;
      border-right: 2px solid var(--border-color);
      position: relative;
      background-color: var(--background-color);
      color: var(--color);
      z-index: 1;
      transition: background-color var(--transition), color var(--transition), border-color var(--transition);
      &:first-child {
        grid-column: 1 / calc((var(--first-size) * 2) + 1);
        position: sticky;
        left: 0;
        z-index: 2;
        text-align: left;
        padding: calc(var(--padding) / 2);
      }
    }
    .info {
      display: grid;
      grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
      text-align: center;
      background-color: var(--table);
      color: var(--color);
      font-weight: 700;
      transition: background-color var(--transition), color var(--transition);
      div {
        padding: calc(var(--padding) / 4);
        border-right: 2px solid var(--border-color);
        transition: border-color var(--transition);
        display: flex;
        align-items: center;
        justify-content: center;
        &:first-child {
          grid-column: 1/3;
          border-bottom: 2px solid var(--border-color);
          transition: border-color var(--transition);
          & + div span, & + div + div span {
            opacity: 0.5;
          }
        }
      }
    }
  }
  .service {
    display: grid;
    grid-template-columns: 150px;
    grid-gap: calc(var(--padding) / 2);
    align-items: center;
    .logo img {
      max-width: 100%;
    }
    .data {
      display: none;
      & > div {
        display: grid;
        grid-auto-flow: row;
        grid-gap: calc(var(--padding) / 4);
      }
      .title {
        font-size: 16px;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
      }
      .stats {
        opacity: 0.5;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
    }
  }
  .coff {
    font-weight: 700;
    padding: 5px 10px;
    border-radius: 5px;
    &.red {
      background-color: #FF8D8D;
    }
    &.green {
      background-color: #85DA9D;
    }
  }
</style>
