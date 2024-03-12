<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-1">
        <NuxtLink to="/pengunjung/tambah" class="btn btn-primary mt-3">⬅️Back</NuxtLink>
      </div>
      <div class="col-lg-10">
        <h2 class="text-center mb-4 mt-3 fw-bold">RIWAYAT KUNJUNGAN</h2>
        <div class="my-3">
          <input type="search" class="form-control form-control-lg rounded-5 border-primary bg-secondary" placeholder="Filter..." />
        </div>
        <div class="my-3 text-muted">menampilkan 3 dari 3</div>

        <table class="table table-bordered border-dark table-hover">
          <thead class="fw-bold">
            <tr>
              <td>no</td>
              <td>nama</td>
              <td>kategori</td>
              <td>waktu</td>
              <td>keperluan</td>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>1</td>
              <td>Dita</td>
              <td>Siswa</td>
              <td>22 Februari 2024, 9.00</td>
              <td>Pinjam buku</td>
            </tr>
            <tr>
              <td>2</td>
              <td>Elisa</td>
              <td>Siswa</td>
              <td>2 maret 2024, 8.00</td>
              <td>Mengembalikan buku</td>
            </tr>
            <tr>
              <td>3</td>
              <td>Zul Hilmi</td>
              <td>Guru</td>
              <td>25 Februari 2024, 8.00</td>
              <td>Pinjam buku</td>
            </tr>
          </tbody>
        </table>
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
}
</style>
