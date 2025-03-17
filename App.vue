<script setup>
import { ref } from "vue";

const npm = ref(233510555);
const textinterpolation = ref('ini adalah text interpolation');
const lokasi = ref('');
const Event = ref('Ini adalah Event');
const warna = ref('');
const nilai = ref(0);
function aksi() {
  if (Event.value === 'Ini adalah Event') {
    Event.value = 'Ini adalah Event yang sudah diubah'
    warna.value = 'Blue'
  } else {
    Event.value = "Ini adalah Event"
    warna.value = 'Red'
  }
}
</script>

<template>
<h1>M. Ferza Erlangga</h1>
<div>{{ npm }}</div>
<p>{{ textinterpolation }}</p>
<hr>
<div>Lokasi = {{ lokasi }}</div>
<select v-model="lokasi">
  <option disabled value="">Tentukan Lokasi Anda</option>
  <option>Pekanbaru</option>
  <option>Duri</option>
  <option>Dumai</option>
</select>
<hr>
<div :style="{color :warna}">{{ Event }}</div>
<button @click="aksi">Button</button>
<hr>
  <input type="text" v-model="nilai" placeholder="Masukkan Nilai Anda" />
  <p>Nilai anda : {{ nilai }}</p>
  <p v-if="nilai < 50">Maaf, anda tidak lulus</p>
  <p v-else-if="nilai >= 50 && nilai < 100">Selamat, anda lulus</p>
  <p v-else-if="nilai = 100">Selamat! anda lulus dengan nilai sempurna</p>
  <p v-else>nilai tidak valid, masukkan nilai yang benar</p>

</template>

<style scoped>
</style>

