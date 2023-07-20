<script setup>
  import { ref } from 'vue'
  let msg = "Hello World Vue.JS";
  let nama = "<h1>Kasir Dudung Tatangkalan</h1>";
  let warna = "Masukan Nama Anda"
  let pesan = "Dudung Selalu Mendukung"
  let message = ref('')
  let picked = ref('Laki-Laki') 
  function peringatan() {
    alert('Pesanan Disimpan')
  }
  function balikanPesan () {
    message.value = message.value.split('').reverse().join('');
  }
</script>
  <template>
    <div>
      <div>{{ msg }}</div>
      <span v-html="nama"></span>
      <span style="color: red;">{{ warna }}</span> <br>
	    <input v-model="message"  />
      <p>Nama Anda: {{ message }}</p>
      <div>Picked: {{ picked }}</div>
        <input type="radio" id="one" value="Laki-Laki" v-model="picked" />
        <label for="one">Laki-Laki</label>
        <input type="radio" id="two" value="Perempuan" v-model="picked" />
        <label for="two">Perempuan</label> <br>
        <span :title="pesan">Terima Kasih Telah Berkunjung Di Dudung Tatangkalan</span>
         <br>
        <button v-on:click="peringatan">Simpan Pesanan</button>

        <!-- split button -->
         <button v-on:click="balikanPesan">Balikan Pesan</button>
    </div>
  </template>