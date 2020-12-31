<template>
  <div>
    <div class="footer">
      <div class="left">
        <a href="#" @click.prevent="clearShopCart">清空购物车</a>
      </div>
       <div class="right">
            <p>商品总价（不含运费）：</p>
            <p><span class="or">{{totalPrice}}</span> 元</p>
            <p>可获积分<span class="or">{{totalIntegral}}</span>点</p>
            <p class="shou"><img src="image/taobao_subtn.jpg" alt=""></p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
props: ['totalIntegral','totalPrice'],
    methods: {
        clearShopCart() {
            this.$emit('faclear')
        }
    },
};
</script>

<style scoped>
.footer {
    display: flex;
    justify-content: space-between;
}
.left { width:  200px;  padding-top: 50px;}

.right { width:  200px;  height: 200px;}
.right p {
    text-align: right;
    line-height: 30px;
}
.or {
    color: orangered;
    font-weight: bold;
    font-size: 20px;
}
.shou {
    cursor: pointer;
}
</style>