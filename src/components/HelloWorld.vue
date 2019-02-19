<template>
  <div>
        <b id="judul">Silahkan pilih barang</b>
        <div v-for="(a, index) in menu" :class="a.active?'unselect':'selected'">
        <div href="#" @click ='pilih(index)' class="pilihan">
        <b class="kiri">{{a.barang}}</b>
        <b class="kanan">$ {{a.harga}}</b>
        </div>
        </div>
        <div class="pilihan total">
        <b class="kiri hasil">total : </b>
        <b class="kanan hasil">$ {{total}}</b>
        </div>
        <button class="tombol" @click='lanjut'> lanjut ke pembayaran </button>
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
                {barang: 'monitor samsung', active:false, harga:2000},
                {barang: 'monitor hp', active:false, harga:3000},
                {barang: 'monitor logitec', active:false, harga:4000},
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
        lanjut(){
            alert('total tagihan : $' + this.total + '.')
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
  color: orange;
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
}
.selected{
  background: red;
}
.kanan{
  float: right;
}
.total{
  border-top: 1px solid orange;
  border-bottom: 1px solid orange;
}
.hasil{
  color: green;
}
.tombol{
  font-size: 20px;
  padding: 10px;
  border: 1px grey solid;
  display: block;
  margin: 0 auto;
  color: yellow;
  margin-top: 30px;
}
.tombol:hover{
  background: orange;
  color:white;
}
</style>
