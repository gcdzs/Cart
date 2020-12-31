<template>
  <div class="shop">
    <Header />
    <div class="line1">
      <p class="p1">店铺宝贝</p>
      <p class="p2">积分</p>
      <p class="p3">单价</p>
      <p class="p4">数量</p>
    </div>

    <dl v-for="(item, index) in goods" :key="index">
      <dt>
        店铺：<a href="#">{{ item.shop }}</a> 卖家：<a href="#">{{
          item.seller
        }}</a>
        <img src="../assets/image/taobao_relation.jpg" alt="" />
      </dt>
      <dd v-for="(item1, j) in item.goodslist" :key="j">
        <div><img :src="item1.goodsimg" alt="" /></div>
        <div class="two">
          <p>
            <a href="#">{{ item1.goodsname }}</a>
          </p>
          <p>{{ item1.goodsmsg }}</p>
          <p>保障：<img src="../assets/image/taobao_icon_01.jpg" alt="" /></p>
        </div>
        <div>
          <strong>{{ item1.integral }}</strong>
        </div>
        <div>{{ item1.price }}</div>
        <div>
          <button class="jia" @click="reduce(item1)">-</button>
          <input
            type="text"
            name=""
            v-model="item1.number"
            readonly
            class="txt"
          />
          <button class="jian" @click="add(item1)">+</button>
        </div>
      </dd>
    </dl>
    <Footer
      :totalPrice="totalPrice"
      :totalIntegral="totalIntegral"
      @faclear="onClear"
    />
  </div>
</template>

<script>
import Header from "./header.vue";
import Footer from "./footer.vue";
export default {
  data() {
    return {
      totalIntegral: 0,
      totalPrice: 0,
      goods: [
        {
          shop: "纤巧百媚时尚鞋坊",
          seller: "纤巧百媚",
          goodslist: [
            {
              goodsname:
                "日韩流行风时尚美眉最爱独特米字拼图金属坡跟公主靴子黑色",
              goodsmsg: "颜色：棕色 尺码：37",
              number: 1,
              price: 100,
              goodsimg: "./image/taobao_cart_01.jpg",
              integral: 5,
            },
            {
              goodsname: "chanel/香奈尔/香奈尔炫亮魅力唇膏3.5g",
              goodsmsg: "",
              number: 1,
              goodsimg: "./image/taobao_cart_02.jpg",
              price: 265,
              integral: 12,
            },
          ],
        },
        {
          shop: "香港我的美丽日记",
          seller: "taobao豆豆",
          goodslist: [
            {
              goodsname:
                "相宜促销专供 大S推荐 最好用的LilyBell化妆棉 好用/推荐/",
              goodsmsg: "",
              number: 1,
              goodsimg: "./image/taobao_cart_04.jpg",
              price: 100,
              integral: 10,
            },
          ],
        },
      ],
    };
  },
  components: {
    Header,
    Footer,
  },

  created() {
    this.goods.forEach((item) => {
      item.goodslist.forEach((item1) => {
        this.totalIntegral += item1.integral;
        this.totalPrice += item1.number * item1.price;
      });
    });
  },

  methods: {
    add(item1) {
      item1.number += 1;
      this.totalPrice += item1.price;
      this.totalIntegral += item1.integral;
    },
    reduce(item1) {
      if (item1.number <= 1) {
        return;
      }
      item1.number -= 1;
      this.totalPrice -= item1.price;
      this.totalIntegral -= item1.integral;
    },
    onClear() {
      this.goods = [];
      this.totalPrice = 0;
      this.totalIntegral = 0;
    },
  },
};
</script>

<style scoped>
.shop {
  width: 1000px;
  margin: 0 auto;
}
.line1 {
  display: flex;
  text-align: center;
  margin: 10px 0;
  border-bottom: 5px solid rgb(75, 174, 219);
  
}

.line1 .p1 {
  flex-grow: 1;
}
.line1 .p2 {
  width: 60px;
}
.line1 .p3 {
  width: 80px;
}
.line1 .p4 {
  width: 100px;
}
dl dt {
  vertical-align: middle;
}
dd {
  display: flex;
  align-items: center;
  background-color: rgb(207, 220, 247);
  height: 100px;
  margin-bottom: 2px;
}
dd div:not(.two) {
  height: 100px;
  border-left: 2px solid #fff;
  border-right: 2px solid #fff;
  display: flex;
  align-items: center;
  justify-content: center;
}
dd div:nth-of-type(1) {
  width: 100px;
}
dd div:nth-of-type(2) {
  flex-grow: 1;
  text-align: left;
  padding-left: 10px;
}
dd div:nth-of-type(3) {
  width: 80px;
}
dd div:nth-of-type(4) {
  width: 80px;
}
dd div:nth-of-type(5) {
  width: 80px;
}
dd div:nth-of-type(5) input {
  width: 20px;
}
.txt {
  margin: 0 3px;
  text-align: center;
}
.jia,
.jian {
  padding: 0 5px;
  cursor: pointer;
}
</style>