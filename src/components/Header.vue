<template>
  <div class="header">
    <logo/>
  </div>
</template>

<script>
import logo from '@/components/logo'

export default {
  components: {logo}
}
</script>

<style lang="scss" scoped>
.header {
  position: fixed;
  top: 40px;
  left: 40px;
  z-index: 5;
  @media screen and (max-width: 768px) {
    left: 20px;
    top: 30px;
  }
}
</style>