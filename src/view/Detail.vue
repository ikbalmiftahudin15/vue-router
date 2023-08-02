<template>
  <br>
  <br>
  <center>
  <div v-if="detail == undefined">ID YANG ANDA CARI TIDAK TERDAFTAR</div>
  <div v-else>
    <img :src="getImgSrc(detail.img)" alt="Category Image">
  <h1>Detail {{ detail.nama }}</h1>
  <p>{{ detail.dekripsi }}</p>
  <h4>Harga : {{ detail.harga }}</h4>
</div>
</center>
</template>

<script>
import { produk } from '../assets/Produk';

export default {
  props: ['id_produk'],
  setup(props) {
    const getImgSrc = (imgFileName) => {
        return '../src/assets/img/' + imgFileName + '' ;
      }
    const detail = produk['produk'].find(function (item) {
      return item.id == props.id_produk;
    });
    return {
      detail,
      getImgSrc
    };
  },
};
</script>

<style>
img{
  height: 260px;
  height: 260px;
}
</style>