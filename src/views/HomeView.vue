<template>
  <div class="container">
    <h1>Masukkan Nama Anda</h1>
    <input type="text" v-model="nama" placeholder="Masukkan nama Anda">
    <button @click="acakNama">Submit</button>
    <div v-if="hasilNama" class="result">
      <p class="result-text">Selamat <span class="nama-highlight">{{ nama }}</span>,</p>
      <p class="result-text">Khodam Kamu Adalah <span class="hasil-highlight">{{ hasilNama }}</span></p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nama: '',
      Khodam: [
        'Pengker', 'Sepiteng Bocor', 'Buto Ijo', 'Rawa Rontek',
        'Nyai Roro Kidul', 'Tuyul', 'Pontianak', 'Telor Busuk'
      ],
      hasilNama: ''
    };
  },
  methods: {
    acakNama() {
      const RandomKhodam = this.Khodam[Math.floor(Math.random() * this.Khodam.length)];
      this.hasilNama = RandomKhodam;
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 400px;
  margin: auto;
  text-align: center;
  padding: 20px;
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  font-family: 'Poppins', sans-serif; /* Menggunakan font Poppins */
}

input[type="text"] {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

button:hover {
  background-color: #45a049;
}

.result {
  margin-top: 20px;
  padding: 10px;
  background-color: #dff0d8;
  border: 1px solid #d6e9c6;
  border-radius: 4px;
}

.result-text {
  margin: 0;
  font-size: 18px;
}

.nama-highlight {
  font-weight: bold;
  color: #007bff; /* blue */
}

.hasil-highlight {
  font-style: italic;
  color: #28a745; /* green */
}
</style>
