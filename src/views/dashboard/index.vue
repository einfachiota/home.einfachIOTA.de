<template>
  <div class="dashboard-container">
    <div class="dashboard-text">name: {{ name }}</div>
    <PanelKpi />
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import PanelKpi from './components/PanelKpi'
export default {
  name: 'Dashboard',
  components: { PanelKpi },
  computed: {
    ...mapGetters([
      'name'
    ])
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
