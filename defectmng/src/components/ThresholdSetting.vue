<!-- 阀值设置 -->
<template>
  <div class="modal">
    <span class="item-title">返工缺陷数阀值：</span>
    <Row>
      <Col span="8">橙色预警：
        <Input type="text" placeholder="正整数" v-model="dashBoardRedev.action"/>
      </Col>
      <Col span="7" offset="1">红色预警：
        <Input type="text" placeholder="正整数" v-model="dashBoardRedev.warnning"/>
      </Col>
      <Col span="7" offset="1">最大值：
        <Input type="text" placeholder="正整数" v-model="dashBoardRedev.max"/>
      </Col>
    </Row>
    <span class="item-title">超48小时未解决缺陷数阀值：</span>
    <Row>
      <Col span="8">橙色预警：
        <Input type="text" placeholder="正整数" v-model="dashBoard48Hour.action"/>
      </Col>
      <Col span="7" offset="1">红色预警：
        <Input type="text" placeholder="正整数" v-model="dashBoard48Hour.warnning"/>
      </Col>
      <Col span="7" offset="1">最大值：
        <Input type="text" placeholder="正整数" v-model="dashBoard48Hour.max"/>
      </Col>
    </Row>
    <span class="item-title">24小时内未解决缺陷数阀值：</span>
    <Row>
      <Col span="8">橙色预警：
        <Input type="text" placeholder="正整数" v-model="dashBoard24Hour.action"/>
      </Col>
      <Col span="7" offset="1">红色预警：
        <Input type="text" placeholder="正整数" v-model="dashBoard24Hour.warnning"/>
      </Col>
      <Col span="7" offset="1">最大值：
        <Input type="text" placeholder="正整数" v-model="dashBoard24Hour.max"/>
      </Col>
    </Row>
  </div>
</template>
<script>
export default {
  data() {
    return {
      dashBoardRedev: {},
      dashBoard48Hour: {},
      dashBoard24Hour: {}
    };
  },
  methods: {
    //获取阀值设置的值
    getThresholdSettings: function() {
      return {
        dashBoardRedev: {
          action: this.dashBoardRedev.action,
          warnning: this.dashBoardRedev.warnning,
          max: this.dashBoardRedev.max
        },
        dashBoard48Hour: {
          action: this.dashBoard48Hour.action,
          warnning: this.dashBoard48Hour.warnning,
          max: this.dashBoard48Hour.max
        },
        dashBoard24Hour: {
          action: this.dashBoard24Hour.action,
          warnning: this.dashBoard24Hour.warnning,
          max: this.dashBoard24Hour.max
        }
      };
    },
    //页面加载时就初始化设置的值
    initDashBoardSetting: function(data) {
      this.dashBoardRedev = data.dashBoardRedev;
      this.dashBoard48Hour = data.dashBoard48Hour;
      this.dashBoard24Hour = data.dashBoard24Hour;
    },
    validateValue:()=>{
      
    }

  }
};
</script>
<style>
.item-title {
  font-size: 15px;
  font-weight: bolder;
}
</style>
