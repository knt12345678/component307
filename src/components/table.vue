<template>
  <div id="table">
    <table class="table table-hover" v-for="(item,index) in cart" :key="index">
      <thead>
        <tr>
          <th scope="col">picture</th>
          <th scope="col">Name</th>
          <th scope="col">quantity</th>
          <th scope="col">price</th>
          <th scope="col">total</th>
          <th scope="col">Delete</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>
            <img :src="item.pic" width="60px" height="80px" />
          </td>
          <td>{{item.name}}</td>
          <td>
            <i class="fa fa-minus minus" @click="minusQty(item),sendData()"></i>
            {{item.quantity}}
            <i
              class="fa fa-plus plus"
              @click="plusQty(item),sendData()"
            ></i>
          </td>

          <td>{{item.price}}</td>
          <td>{{item.total}}</td>
          <b-button @click="removeProduct(product)">ลบ</b-button>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    cart: Array,
  },
  methods: {
    plusQty: function (list) {
      list.quantity += 1;
      list.total = list.quantity * list.price;
    },
    minusQty: function (list) {
      list.quantity -= 1;
      if (list.quantity <= 1) {
        list.quantity = 1;
      }
      list.total = list.quantity * list.price;
    },
    sendData() {
      this.$emit("onCal", this.plusQty, this.minusQty, this.removeProduct);
    },
    removeProduct(list) {
      if (confirm("คุณต้องการลบหรือไม่ ?")) {
        var index = this.cart.indexOf(list);
        this.cart.splice(index, 1);
        if (list.id == 1) {
          this.p1 = 0;
        } else {
          this.p2 = 0;
        }
      }
    },
  },
};
</script>

<style>
.minus {
  cursor: pointer;
  margin-right: 10px;
}
.plus {
  cursor: pointer;
  margin-left: 10px;
}
</style>