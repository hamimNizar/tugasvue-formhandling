<template>
  <div class="home">
    <h1>Data Mahasiswa</h1>
    <div class="container mt-5">
      <div class="row justify-content-center">
        <form class="row g-3" v-on:submit.prevent>
          <div class="col-md-6">
            <label for="inputNim" class="form-label">NIM</label>
            <input type="text" class="form-control" id="inputNim" v-model="mahasiswa.nim">
          </div>
          <div class="col-md-6">
            <label for="inputJurusan" class="form-label">Jurusan</label>
            <input type="text" class="form-control" id="inputJurusan" v-model="mahasiswa.jurusan">
          </div>
          <div class="col-12">
            <label for="inputNama" class="form-label mt-5">Nama</label>
            <input type="text" class="form-control" id="inputNama" placeholder="nama lengkap" v-model="mahasiswa.nama">
          </div>
          <div class="col-12">
            <label for="inputAlamat" class="form-label mt-5">Alamat</label>
            <input type="text" class="form-control" id="inputAlamat" placeholder="Alamat lengkap" v-model="mahasiswa.alamat">
          </div>
          <div class="col-12">
            <button type="submit" class="btn btn-primary mt-5" @click="kirim">Kirim</button>
          </div>
        </form>
        
      </div>
      <div class="row justify-content-center">
        <div class="col mt-3">
          <p> {{ mahasiswa }} </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import axios from "axios";

export default {
  name: 'Home',
  components: {
    
  },
  data() {
      return {
        mahasiswa:{}
      }
  },
  methods:{
    kirim(){
      console.log(this.mahasiswa)
      axios
        .post("http://localhost:3000/mahasiswa", this.mahasiswa)
        .then(() => {
          console.log("berhasil");
          this.$router.push({ path: "/about"})
        })
        .catch((err) => {
          console.log(err);
        })
    }
  },
  mounted(){

  }
}
</script>
