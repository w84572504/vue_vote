<template>
  <div>
    <div class="content" v-html="$store.state.db.answer"></div>

    <div v-if="$store.state.db.start_time*1000 < timestamp" style="padding: 14px;">
      <h3>活动规则</h3>
      <h4>（一）【礼物功能郑重说明】</h4>
      <p>
        1、赠送一点礼物为一元钱可自动兑换票数5票（每个礼物对应的点数不同）。
      </p>
      <p>
        2、赠送礼物除增加票数外无任何其他功能，所有礼物均为用户自愿购买，购买礼物后本平台概不退换。
      </p>
      <p>
        3、活动重在参与，意在宣传推广，礼物设置与校区无关。不提倡赠送礼物，赠送礼物为投票系统自带功能，目的是为了防止外部刷票造成服务器混乱。
      </p>
      <h4>（二）【温馨提示】</h4>
      <p>1、活动期间每个微信号每天可投3票，分别投给三个不同选手，同一选手一个用户限投1票。 </p>
      <p>2、比赛成绩以活动截止时间点票数为准，排名由高到低排序。 </p>
      <p>3、活动以友好、和谐、丰富文化生活为宗旨！礼品价值有限，请不要恶意攀比，恶意竞争！ </p>
      <p>4、活动期间如出现异常，属于短时间内投票人数过多造成，请确保网络正常再重新打开链接进行正常投票。 </p>

      <h4>（三）【禁止刷票】</h4>
      <p>平台采取24小时动态监测，智能拦截网络刷票数据（时间、环境、热度、IP、曲线峰值等），严厉杜绝网络作弊投票行为，活动过程中如果发现票数异常，本平台将对网络刷票者做出减票、锁定，严重者将取消其参赛资格，滚动字幕公之于众等方法处理。我们将保留作弊投票行为之截图、监控数据库作为证据保留。希望大家积极举报有恶意刷票之行为。</p>

      <h4>（四）【其他注意事项】</h4>
      <p>1、禁止用他人照片或冒用他人名义参赛，一经发现，取消其参赛资格。</p>
      <p>2、一旦参赛，本活动即认定参赛者提供了自己照片的合法使用授权，不再另行协议。</p>
      <p>3、本活动秉持公平、公正、公开原则，对蓄意诽谤、破坏、干扰活动的言论及行为，本平台将会严肃处理，情节严重者，本公司将通过法律手段维护本次活动的合法权益。</p>
      <p>4、因网络波动原因，若出现系统时间与当地时间不符等情况，以系统倒计时时间为准。</p>
      <p>5、参与本次活动则视为同意并接受本次活动的所有规则，本平台拥有本次活动的最终解释权！</p>
    </div>
  </div>
</template>

<script>
export default {
  // 奖品
  name: "prize",
  data() {
    return {
      timestamp: Date.parse(new Date())
    }
  },
  mounted() {
    document.title = "活动奖品"
    console.log("当前时间----", this.timestamp);
    console.log("当前时间----", new Date(this.timestamp));
    console.log("活动开始时间", this.$store.state.db.start_time * 1000);
    console.log("活动开始时间", new Date(this.$store.state.db.start_time * 1000));
  }
};
</script>

<style scoped>
.content {
  padding: 0 14px;
}

p {
  line-height: 1.5em;
  letter-spacing: 1.2px;
}
</style>
