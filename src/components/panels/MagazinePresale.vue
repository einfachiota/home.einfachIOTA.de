<template>
  <el-col :xs="12" :sm="12" :lg="6" class="card-panel-col">
    <div class="card-panel" @click="handleSetLineChartData('newVisitis')">
      <div class="card-panel-icon-wrapper icon-people">
          <img class="icon" src="@/assets/icons/eimag-1--EN-1.svg" />
      </div>
      <div class="card-panel-description">
        <div class="card-panel-text">Presale EN Active</div>
        <count-to :start-val="0" :end-val="count" :duration="3600" class="card-panel-num" />
      </div>
    </div>
  </el-col>
</template>

<script>
import axios from "axios";
import CountTo from 'vue-count-to'

export default {
  components: {
    CountTo
  },
  data() {
    return {
      count: 0
    };
  },
  created() {
    axios
      .get("", {})
      .then(response => (this.count = 21));//response.amount));
  }
};
</script>

<style lang="scss" scoped>
.panel-group {
  margin-top: 18px;
  .card-panel-col {
    margin-bottom: 32px;
  }
  .card-panel {
    height: 108px;
    cursor: pointer;
    font-size: 12px;
    position: relative;
    overflow: hidden;
    color: #666;
    background: #fff;
    box-shadow: 4px 4px 40px rgba(0, 0, 0, .05);
    border-color: rgba(0, 0, 0, .05);
    .icon {
      position: absolute;
      height: 70%;
    }
    .card-panel-icon-wrapper {
      float: left;
      margin: 14px 0 0 14px;
      padding: 16px;
      transition: all 0.38s ease-out;
      border-radius: 6px;
    }
    .card-panel-icon {
      float: left;
      font-size: 48px;
    }
    .card-panel-description {
      float: right;
      font-weight: bold;
      margin: 26px;
      margin-left: 0px;
      .card-panel-text {
        line-height: 18px;
        color: rgba(0, 0, 0, 0.45);
        font-size: 16px;
        margin-bottom: 12px;
      }
      .card-panel-num {
        font-size: 20px;
      }
    }
  }
}
@media (max-width:550px) {
  .card-panel-description {
    display: none;
  }
  .card-panel-icon-wrapper {
    float: none !important;
    width: 100%;
    height: 100%;
    margin: 0 !important;
    .svg-icon {
      display: block;
      margin: 14px auto !important;
      float: none !important;
    }
  }
}
</style>