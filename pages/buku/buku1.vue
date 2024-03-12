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
          <img src="~/assets/img/Bincang_Akhlak.jpg" class="cover" alt="cover 1" />
        </div>
        <div class="col">
          <div class="mb-5">
            <h6>Rak: 800</h6>
            <h6>Kategori: Kesusastraan</h6>
            <h6>Judul: Bincang Akhlak</h6>
            <h6>Penulis: Takdir Alisyahbana Ridwan</h6>
            <h6>Penerbit: Mediakita</h6>
            <h6>Tahun terbit: 2019</h6>
            <h6>Jumlah hal: 256</h6>
            <h6>Sinopsis/deskripsi:</h6>
            <p>
              “Bro, kayaknya lagi ada masalah. Ada apa? Coba cerita, kali aja bisa bantu apa gitu,” kataku sambil menatap matanya. “Iya, nih. Ada orang yang nagih utang ke aku, tapi duitku nggak cukup untuk bayar,” jawabnya sambil balas
              menatapku. “Oh, masalah itu. Kurang berapa?” “Mau bantu, Jek?” Matanya berbinar-binar. “Berapa emang?” “Kurang 2 juta.” Aku langsung ngeluarin dompet, terus ngambil kartu nama. “Di sini ada nomor telepon yang bisa kamu hubungi
              kalau mau gadai BPKB motor, ya.” Dia langsung pulang nggak pake salam. Sepertinya, suasana hatinya lagi nggak enak. “Seiring bertambahnya usia, semakin sadar kalau uang tidak bisa membeli kebahagiaan, kecuali banyak,” Takdir
              Alisyahbana Ridwan
            </p>
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
