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
          <img src="~/assets/img/demung.jpg" class="cover" alt="cover 2" />
        </div>
        <div class="col">
          <div class="mb-5">
            <h6>Rak: 800</h6>
            <h6>Kategori: Kesusastraan</h6>
            <h6>Judul: Demung Janggala</h6>
            <h6>Penulis: Tatang</h6>
            <h6>Penerbit: CV. Geger sunten agurtus</h6>
            <h6>Tahun terbit: 1993</h6>
            <h6>Jumlah hal: 232</h6>
            <h6>Sinopsis/deskripsi:</h6>
            <p>
              Novel ini menceritakan tokoh utama yaitu Demung Janggala atau Surapamungkas dan kakaknya Listayuwangi/Lismaya. Mereka berdua di ajak kabur oleh penjaganya yaitu Mamang Jalaprang. Mereka harus kabur dikarenakan di Dayeuh Ukur
              sedang terjadi keributan antara kanjeng Adipati Mataram.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 205px;
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
