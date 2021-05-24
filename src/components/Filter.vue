<template>
  <div id="filter">
    <div class="row" data-columns="3">
      <div class="wrap">
        <button class="button"><span><span class="type"><i class="icon crown"></i></span><span class="name">Победа</span><span class="count">(21)</span></span></button>
        <button class="button"><span><span class="type"><i class="icon target"></i></span><span class="name">Тоталы</span><span class="count">(751)</span></span></button>
        <button class="button"><span><span class="type"><i class="icon plus-minus"></i></span><span class="name">Форы</span><span class="count">(91)</span></span></button>
        <button class="button"><span><span class="type"><i class="icon target-user"></i></span><span class="name">Инд. тоталы</span><span class="count">(21)</span></span></button>
        <button class="button"><span><span class="type"><i class="icon angle"></i></span><span class="name">Угловые</span><span class="count">(41)</span></span></button>
      </div>
    </div>
    <div class="row" data-columns="3">
      <div class="wrap">
        <button class="alternative"><span><span class="type"><i class="icon crown"></i></span><span class="name">Победа</span><span class="count">(21)</span></span></button>
        <button class="alternative"><span><span class="type"><i class="icon target"></i></span><span class="name">Тоталы</span><span class="count">(751)</span></span></button>
        <button class="alternative"><span><span class="type"><i class="icon plus-minus"></i></span><span class="name">Форы</span><span class="count">(91)</span></span></button>
        <button class="alternative"><span><span class="type"><i class="icon target-user"></i></span><span class="name">Инд. тоталы</span><span class="count">(21)</span></span></button>
        <button class="alternative"><span><span class="type"><i class="icon angle"></i></span><span class="name">Угловые</span><span class="count">(41)</span></span></button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Filter'
}
</script>

<style scoped lang="scss">
  #filter {
    display: grid;
    grid-gap: var(--padding);
    grid-auto-flow: column;
    padding-left: var(--padding);
    padding-right: var(--padding);
    grid-auto-columns: minmax(0, 1fr);
    align-items: center;
  }
  .row {
    position: relative;
    .wrap {
      display: grid;
      grid-gap: calc(var(--padding) / 2);
      grid-auto-columns: auto;
      grid-template-columns: repeat(1, auto);
    }

    @each $column in [1,2,3,4,5,6,7,8,9,10] {
      &[data-columns="#{$column}"] .wrap {
        grid-template-columns: repeat(#{$column}, auto);
      }
    }
    &:first-child {
      &:after {
        content: '';
        width: 3px;
        height: 100%;
        background-color: var(--button-background-color);
        position: absolute;
        right: calc((var(--padding) * -0.5) - 1.5px);
        top: 0;
        border-radius: 10px;
        transition: background-color var(--transition);
      }
    }
  }
  .button, .alternative {
    font-size: 14px;
    padding: 7px 15px;
    border-radius: 7px;
    width: 100%;
    & > span {
      display: inline-grid;
      grid-gap: 10px;
      grid-auto-flow: column;
      align-items: center;
    }
    .name {
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }
    .icon {
      font-size: 18px;
    }
  }
</style>
