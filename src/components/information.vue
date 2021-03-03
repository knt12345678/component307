<template>
  <div id="information">
    <div class="container">
      <div class="row">
        <div class="col-md-4 b-card text-center bcard" v-for="list in product" :key="list.id">
          <b-card
            :title="list.nameProduct"
            :img-src="list.picProduct"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>ราคา&nbsp;{{ list.price }}&nbsp;บาท</b-card-text>
            <b-button
              align="left"
              variant="primary"
              @click="addCart(list),sendData()"
            >เพิ่มไปที่รถเข็น</b-button>
          </b-card>
        </div>
      </div>
      <footer class="footer"></footer>
    </div>
    <h4 class="price" v-if="cart!=0" align="center">ยอดชำระเงินทั้งหมด&nbsp;{{total()}}&nbsp;บาท</h4>
  </div>
</template>
<script>
export default {
  name: "information",
  props: {
    product: Array,
    plus: Number,
    minus: Number,
  },

  data() {
    return {
      cart: [],
      p1: 0,
      p2: 0,
      p3: 0,
      p4: 0,
      p5: 0,
      p6: 0,
      p7: 0,
      p8: 0,
    };
  },

  methods: {
    addCart(list) {
      var found;
      if (list.id == 1) {
        this.p1 += 1;
        if (this.p1 <= 1) {
          //ซื้อรอบเดียว
          this.pushList(list);
        } else {
          //ซื้อซ้ำ
          found = this.findID(list);
          this.cart[found].quantity += 1;
          this.cart[found].total =
            this.cart[found].quantity * this.cart[found].price;
        }
      } else if (list.id == 2) {
        this.p2 += 1;
        if (this.p2 <= 1) {
          //ซื้อรอบเดียว
          this.pushList(list);
        } else {
          //ซื้อซ้ำ
          found = this.findID(list);
          this.cart[found].quantity += 1;
          this.cart[found].total =
            this.cart[found].quantity * this.cart[found].price;
        }
      } else if (list.id == 3) {
        this.p3 += 1;
        if (this.p3 <= 1) {
          //ซื้อรอบเดียว
          this.pushList(list);
        } else {
          //ซื้อซ้ำ
          found = this.findID(list);
          this.cart[found].quantity += 1;
          this.cart[found].total =
            this.cart[found].quantity * this.cart[found].price;
        }
      } else if (list.id == 4) {
        this.p4 += 1;
        if (this.p4 <= 1) {
          //ซื้อรอบเดียว
          this.pushList(list);
        } else {
          //ซื้อซ้ำ
          found = this.findID(list);
          this.cart[found].quantity += 1;
          this.cart[found].total =
            this.cart[found].quantity * this.cart[found].price;
        }
      } else if (list.id == 5) {
        this.p5 += 1;
        if (this.p5 <= 1) {
          //ซื้อรอบเดียว
          this.pushList(list);
        } else {
          //ซื้อซ้ำ
          found = this.findID(list);
          this.cart[found].quantity += 1;
          this.cart[found].total =
            this.cart[found].quantity * this.cart[found].price;
        }
      } else if (list.id == 6) {
        this.p6 += 1;
        if (this.p6 <= 1) {
          //ซื้อรอบเดียว
          this.pushList(list);
        } else {
          //ซื้อซ้ำ
          found = this.findID(list);
          this.cart[found].quantity += 1;
          this.cart[found].total =
            this.cart[found].quantity * this.cart[found].price;
        }
      }
    },

    pushList(list) {
      this.cart.push({
        id: list.id,
        pic: list.picProduct,
        name: list.nameProduct,
        quantity: 1,
        price: list.price,
        total: list.price,
      });
    },
    findID: function (item) {
      for (var i = 0; i < this.cart.length; i++) {
        if (this.cart[i].id == item.id) {
          return i; //ตำแหนงสินค้าที่ค้นเจอในตะกร้า
        }
      }
      return -1;
    },

    total: function () {
      var sum = 0;
      this.cart.forEach(function (item) {
        sum += item.total;
      });
      return sum;
    },
    sendData() {
      this.$emit("onCart", this.cart);
    },
  },
};
</script>

<style>
.bcard {
  padding-top: 50px;
}
.footer {
  padding-bottom: 50px;
}
</style>