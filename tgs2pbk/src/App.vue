<template>
  <div class="container">
    <h1>Pencari Sayuran</h1>
    <input type="text" v-model="cari" class="input-cari" :style="{ width: ukuranInput + 'px' }" />
    <button @click="cariKata">Cari</button>
    <ul class="hasil-pencarian">
      <li v-for="kata in hasilPencarian" :key="kata">{{ kata }}</li>
    </ul>

  
  </div>
</template>

<script>

export default {
  data() {
    return {
      cari: "",
      hasilPencarian: [],
      ukuranInput: 200,
    };
  },
  methods: {
    cariKata() {
      const kataCari = this.cari.toLowerCase();
      this.hasilPencarian = ["bayam","sawi","tomat","kangkung","brokoli","kol","singkong","kacang panjang","buncis","pare","timun","terong","wortel","kentang"].filter(kata => kata.includes(kataCari));
    },
    perbesarInput() {
      if (this.ukuranInput < 500) {
        this.ukuranInput += 50;
      }
    },
    perkecilInput() {
      if (this.ukuranInput > 100) {
        this.ukuranInput -= 50;
      }
    },
  },

  
};
</script>

<style scoped>
.container {
  text-align: center;
  padding: 20px;
}

.input-cari {
  padding: 10px;
  border: 1px solid #a40d0d;
}

.hasil-pencarian {
  list-style: none;
  padding: 0;
}

.hasil-pencarian li {
  padding: 10px;
  border-bottom: 1px solid #cccccc;
}
</style>