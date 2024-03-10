<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-sm-3">
        <NuxtLink to="/" class="btn btn-primary mt-3">⬅️Back to home</NuxtLink>
      </div>
      <div class="col-sm-5">
        <h2 class="text-center my-4">ISI BUKU KUNJUNGAN</h2>

        <form>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg rounded-5" placeholder="Nama" />
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KEANGGOTAAN</option>
              <option value="siswa">Siswa</option>
              <option value="Guru">Guru</option>
              <option value="Staf">Staf</option>
            </select>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5 mb-2">
              <option value="kelas">KELAS</option>
              <option value="kelas">X</option>
              <option value="kelas">XI</option>
              <option value="kelas">XII</option>
            </select>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5 mb-2">
              <option value="jurusan">JURUSAN</option>
              <option value="jurusan">PPLG</option>
              <option value="jurusan">TJKT</option>
              <option value="jurusan">TBSM</option>
              <option value="jurusan">TOI</option>
              <option value="jurusan">DKV</option>
            </select>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KEPERLUAN</option>
              <option value="baca">Baca buku</option>
              <option value="pinjam">Pinjam Buku</option>
              <option value="pengembalian">Mengembalikan buku</option>
            </select>
          </div>
          <div class="col-lg-3">
            <NuxtLink to="/pengunjung" class="btn btn-primary text-dark btn-lg rounded-4 px-3">KIRIM</NuxtLink>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 203px;
}
</style>
