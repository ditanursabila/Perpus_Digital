<template>
  <div class="container-fluid">
    <div class="row">
      <div>
        <NuxtLink to="/" class="btn btn-primary mt-3">⬅️Back to home</NuxtLink>
      </div>
      <div class="col-lg-12">
        <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
        <div class="my-3">
          <input type="search" class="form-control form-control-lg rounded-5" placeholder="FILTER" />
        </div>
        <div class="my-3 text-muted">menampilkan 7 dari 15</div>

        <table class="table table-hover">
          <thead class="table-dark">
            <tr>
              <td>NO</td>
              <td>NAMA</td>
              <td>KATEGORI</td>
              <td>WAKTU</td>
              <td>KEPERLUAN</td>
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
              <td>Sasta</td>
              <td>Siswa</td>
              <td>29 Februari 2024, 9.10</td>
              <td>Baca buku</td>
            </tr>
            <tr>
              <td>4</td>
              <td>Zul Hilmi</td>
              <td>Guru</td>
              <td>25 Februari 2024, 8.00</td>
              <td>Pinjam buku</td>
            </tr>
            <tr>
              <td>5</td>
              <td>Deni</td>
              <td>Guru</td>
              <td>26 Februari 2024, 13.00</td>
              <td>pinjam buku</td>
            </tr>
            <tr>
              <td>7</td>
              <td>Mirna</td>
              <td>Siswa</td>
              <td>2 maret 2024, 10.00</td>
              <td>Mengembalikan buku</td>
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
</style>
