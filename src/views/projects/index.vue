<template>
  <div class="app-container">
    <el-row :gutter="40" class="panel-group">
      <el-col
        v-for="(project, index) in projects"
        :key="index"
        :xs="12"
        :sm="12"
        :lg="12"
        class="card-panel-col"
      >
        <div class="card-panel" @click="handleSetLineChartData('shoppings')">
          <div class="card-heading">
            <h2>{{ project.title }}</h2>
          </div>
          <div class="card-panel-description">
            <div class="card-panel-text">{{ project.description }}</div>
          </div>
          <div class="card-panel-preview-wrapper">
            <link-prevue class="card-panel-preview" :url="project.url">
              <template slot-scope="props">
                <div class="card" style="width: 20rem;">
                  <img class="card-img-top" v-if="props.img" :src="props.img" :alt="props.title" />
                  <div class="card-block">
                    <h4 class="card-title">{{props.title}}</h4>
                    <p class="card-text">{{props.description}}</p>
                    <a v-bind:href="props.url" target="_blank" class="link">Discover More</a>
                  </div>
                </div>
              </template>
            </link-prevue>
          </div>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import LinkPrevue from "link-prevue";

export default {
  components: { LinkPrevue },
  data() {
    return {
      projects: [
        {
          title: "IOTA Devnet Faucet",
          url: "https://faucet.einfachiota.de/",
          description: "Sends IOTA Tokens to an IOTA Devnet Address",
          status: "done"
        },
        {
          title: "iota4earth",
          url: "https://iota4earth.org/",
          description:
            "IOTΛ4Earth is an initiative to support projects and people who have a positive impact on our earth.",
          status: "inactive"
        },
        {
          title: "iota.gratis",
          url: "https://github.com/einfachiota/iota.gratis",
          description: "Get your first IOTA token for free!",
          status: "in_progress"
        },
        {
          title: "iota-affiliate-service",
          url: "https://github.com/einfachiota/iota-affiliate-service",
          description:
            "service to process and manage affiliate programs using IOTA and paying IOTA",
          status: "in_progress"
        }
      ]
    };
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
    min-height: 33%;
    height: 700px;
    cursor: pointer;
    font-size: 12px;
    position: relative;
    overflow: hidden;
    color: #666;
    background: #fff;
    box-shadow: 4px 4px 40px rgba(0, 0, 0, 0.05);
    border-color: rgba(0, 0, 0, 0.05);
    .icon {
      position: absolute;
      width: 20%;
    }

    .card-panel-preview-wrapper {
      float: left;
      margin: 14px 0 0 14px;
      padding: 16px;
      transition: all 0.38s ease-out;
      border-radius: 6px;
    }
    .card-panel-preview {
      float: left;
      font-size: 48px;

      border: 1px solid rgba(0, 0, 0, 0.05);

      .card-img-top {
        max-height: 100px;
      }

      .link {
          display: -webkit-box;
        display: flex;
        -webkit-box-pack: center;
        justify-content: center;
        -webkit-box-align: center;
        align-items: center;
        height: 40px;
        padding: 0 30px;
        background-color: var(--light);
        border-radius: 50px;
        font-weight: 900;
        font-size: 14px;
        background-color: var(--primary);
      }
    }
    .card-panel-description {
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
@media (max-width: 550px) {
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