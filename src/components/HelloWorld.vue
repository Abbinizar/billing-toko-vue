<template>
  <div>
    <b id="judul">LIST BARANG</b>
    <div v-for="(a, index) in menu" :class="a.active?'unselect':'selected'">
      <div href="#" @click ='pilih(index)' class="pilihan">
        <b class="">{{a.barang}}</b>
        <b class="kanan">Rp. {{a.harga}}</b>
      </div>
    </div>
    <div class="pilihan total">
      <b class="">TOTAL : </b>
      <b class="kanan">Rp. {{total}}</b>
    </div>
    <button class="tombol" @click='bayar'> Bayar Tagihan </button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  // data () {
  //   return {
  //     msg: 'Welcome to Your Vue.js App'
  //   }
  // },
  data(){
    return{
      menu:[
          {barang: 'Laptop samsung', active:false, harga:2000},
          {barang: 'Laptop hp', active:false, harga:3000},
          {barang: 'Laptop lenovo', active:false, harga:4000},
          {barang: 'Laptop asus', active:false, harga:5000},
          {barang: 'Laptop apple', active:false, harga:6000},
          {barang: 'Laptop acer', active:false, harga:7000},

      ],
      total:0
    }
  },
  methods:{
    pilih(index){
        this.menu[index].active = !this.menu[index].active
        if(this.menu[index].active == true){
            this.total += this.menu[index].harga
        }else if (this.menu[index].active == false){
            this.total -= this.menu[index].harga
        }
    },
    bayar(){
        alert('total tagihan : Rp.' + this.total + '.')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body{
  font-family: sans-serif;
  font-size: 20px;
  color: white;
}
#judul{
  font-size: 35px;
  text-align: center;
  display: block;
  margin-top: 50px;
  margin-bottom: 20px;
  color: blue;
}
#app{
  width: 500px;
  margin: 0 auto;
  display: block;
}
.pilihan{
  padding: 15px;
  margin-top: 5px;
  cursor: pointer;
}
.unselect{
  background: green;
  color: white;
}
.selected{
  background: grey;
  color: white;
}
.kanan{
  float: right;
}
.total{
  border-top: 1px solid red;
  border-bottom: 1px solid red;
}
.hasil{
  color: green;
}
.tombol{
  font-family: sans-serif;
  font-size: 20px;
  padding: 10px;
  border: 1px grey solid;
  display: block;
  margin: 0 auto;
  color: white;
  background: blue;
  margin-top: 30px;
  border-radius: 5%;
}
.tombol:hover{
  background: orange;
  color:white;
}
</style>
