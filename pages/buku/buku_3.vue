<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-sm-1">
        <NuxtLink to="/buku" class="btn btn-primary mt-3">⬅️Back</NuxtLink>
      </div>
      <div class="col-sm-10">
        <h2 class="text-center mb-5 mt-3 fw-bold">DETAIL BUKU</h2>
      </div>
      <div class="flex-container">
        <div class="card">
          <img src="~/assets/img/Bleeding.jpg" class="cover" alt="cover 3" />
        </div>
        <div class="col">
          <div class="mb-5">
            <h6>Rak: 800</h6>
            <h6>Kategori: Kesusastraan</h6>
            <h6>Judul: Bleeding Love</h6>
            <h6>Penulis: Ally Jane</h6>
            <h6>Penerbit: Sheila</h6>
            <h6>Tahun terbit: 2014</h6>
            <h6>Jumlah hal: 370</h6>
            <h6>Sinopsis/deskripsi:</h6>
            <p>Bleeding Love -Saat orang yang kau cintai berada dalam bahaya, tak ada yang lebih penting bagimu selain menyelamatkannya. Bahkan tidak dengan dendam terbesarmu sekalipun-</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 160px;
}
.card {
  width: 20%;
  height: 70%;
  background-color: #d9d9d9;
}
img {
  width: 80%;
  margin-left: 10%;
  margin-top: 5%;
  margin-bottom: 5%;
}
.flex-container {
  display: flex;
  height: 10%;
}
.flex-container > div {
  margin: 20px;
  padding: 0px;
}
</style>
