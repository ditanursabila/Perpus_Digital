<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-1">
        <NuxtLink to="/" class="btn btn-primary mt-3">⬅️Back</NuxtLink>
      </div>
      <div class="col-lg-10">
        <h2 class="text-center mb-4 mt-3 fw-bold">ISI BUKU KUNJUNGAN</h2>

        <form>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg rounded-5 bg-secondary border-secondary" placeholder="NAMA" />
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5 bg-secondary border-secondary">
              <option value="">KEANGGOTAAN</option>
              <option value="siswa">Siswa</option>
              <option value="Guru">Guru</option>
              <option value="Staf">Staf</option>
            </select>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5 mb-2 bg-secondary border-secondary">
              <option value="kelas">KELAS</option>
              <option value="kelas">X PPLG</option>
              <option value="kelas">X TJKT</option>
              <option value="kelas">X TBSM</option>
              <option value="kelas">X TOI</option>
              <option value="kelas">X DKV</option>
              <option value="kelas">XI PPLG</option>
              <option value="kelas">XI TJKT</option>
              <option value="kelas">XI TBSM</option>
              <option value="kelas">XI TOI</option>
              <option value="kelas">XI DKV</option>
              <option value="kelas">XII RPL</option>
              <option value="kelas">XII TKJ</option>
              <option value="kelas">XII TBSM</option>
            </select>
          </div>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg rounded-4 bg-secondary border-secondary" placeholder="KEPERLUAN" />
          </div>
          <div class="col-lg-3">
            <NuxtLink to="/pengunjung/" class="btn btn-primary text-dark btn-lg rounded-5 px-4 border-primary">KIRIM</NuxtLink>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 205px;
}
.bg-secondary {
  background-color: #d9d9d9 !important;
  color: #927d7d;
}

.border-primary {
  border-color: #000aff;
  background-color: #358bda !important;
  box-shadow: 0px 1px 4px #000000;
}
</style>
