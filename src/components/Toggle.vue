<template>
  <div id="toggle">
    <label for="theme-control" id="checkbox"></label>
  </div>
</template>

<script>
export default {
  name: 'Toggle'
}
</script>

<style scoped lang="scss">
  #checkbox {
    display: block;
    background-image: url('../assets/images/toggle-on.svg');
    background-repeat: no-repeat;
    background-position: left top;
    background-size: cover;
    height: 0;
    width: 50px;
    padding-bottom: 55.5555%;
    cursor: pointer;
  }
  #theme-control:checked + #template #checkbox {
    background-image: url('../assets/images/toggle-off.svg');
  }
</style>
