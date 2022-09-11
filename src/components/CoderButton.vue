<template>
  <div>
    <button class="coder--button" @click="getPrice(price)">{{ newLabel }}</button>
    <p v-if="total!==0">Total: ${{ applyDiscount }}</p>
  </div>
</template>

<script>
export default {
  name: 'CoderButton',
  data() {
    return {
      total: 0,
      newLabel: '',
    };
  },
  props: {
    label: {
      type: String,
    },
    price: {
      type: Number,
    },
  },
  mounted() {
    this.newLabel = this.label;
  },
  methods: {
    getPrice(price) {
      this.total = price;
      this.newLabel = 'Buyed!';
      this.$alert('Descuento aplicado');
    },
  },
  computed: {
    applyDiscount() {
      return (this.total - (this.total * 10) / 100);
    },
  },
};
</script>

<style scoped>
.coder--button {
  border-radius: 10px;
  border: none;
  background-color: #393B43;
  color: #E5F876;
  padding: 10px;
  width: 170px;
  cursor: pointer;
}
.coder--button:active {
  box-shadow: 0px 1px 5px 0px #393B43;
}
p {
  margin: 12px 0px 0px 0px;
  color: #fd9001;
  text-align: center;
  font-size: 18px;
}
</style>
