<template>
  <div>
    <div>
      <img src="image/taobao_logo.gif" alt="" />
      <p>您的位置：<a href="#">首页</a>><a href="#">我的淘宝</a>>我的购物车</p>
      <ul class="nav">
        <li>
          <p class="white">查看购物车</p>
          <i></i>
        </li>
        <li class="">
          <p>确认订单信息</p>
          <i></i>
        </li>
        <li>
          <p>付款到支付宝</p>
          <i></i>
        </li>
        <li>
          <p>确认收货</p>
          <i></i>
        </li>
        <li style="border-radius: 3px 0 0 3 px">
          <p>评价</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.white {
  color: white;
}

.nav {
  margin: 10px 0;
  display: flex;
}

.nav li p {
  text-indent: 15px;
}

.nav li:first-child {
  height: 24px;
  line-height: 24px;
  background-color: #ff6600;
  border-radius: 3px 0 0 3 px;
  width: 120px;
}

.nav li {
  height: 24px;
  line-height: 24px;
  background-color: #e4e4e4;
  width: 120px;

  display: flex;
  justify-content: space-between;
}

.nav li i {
  width: 15px;
  height: 24px;
  background-image: url(/image/taobao_bg.png);
  background-repeat: no-repeat;
  display: inline-block;
}

.nav li i .last {
  width: 15px;
  height: 24px;
  background-image: url(/image/taobao_bg.png);
  background-repeat: no-repeat;
  display: inline-block;
  background-position: -12px -140px;
}
</style> 