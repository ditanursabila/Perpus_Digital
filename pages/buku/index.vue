<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-1">
        <NuxtLink to="/" class="btn btn-primary mt-3">⬅️Back</NuxtLink>
      </div>
      <div class="col-lg-10">
        <h2 class="text-center mb-4 mt-3 fw-bold">CARI BUKU</h2>
        <div class="my-3">
          <input type="search" class="form-control rounded-5 bg-secondary border-primary" placeholder="Mau baca apa hari ini?" />
        </div>
        <div class="my-3 text-muted">menampilkan 3 dari 100</div>
        <div class="row">
          <div class="col-sm-2 mb-4 me-5">
            <nuxt-link to="/buku/buku1">
              <div class="card">
                <img src="~/assets/img/Bincang_Akhlak.jpg" class="cover" alt="cover 1" />
                <div class="card-body">
                  <p class="card-text">Bincang akhlak</p>
                </div>
              </div>
            </nuxt-link>
          </div>
          <div class="col-sm-2 mb-4 me-5">
            <nuxt-link to="/buku/buku-2">
              <div class="card">
                <img src="~/assets/img/demung.jpg" class="cover" alt="cover2" />
                <div class="card-body">
                  <p class="card-text">Demung Janggala</p>
                </div>
              </div>
            </nuxt-link>
          </div>
          <div class="col-sm-2 mb-4 me-5">
            <nuxt-link to="/buku/buku_3">
              <div class="card">
                <img src="~/assets/img/Bleeding.jpg" class="cover" alt="cover3" />
                <div class="card-body">
                  <p class="card-text">Bleeding Love</p>
                </div>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card-body {
  width: 100%;
  padding: 0;
}

.container-fluid {
  margin-top: 205px;
}
.card {
  width: 100%;
  height: 100%;
  text-align: center;
  background-color: #d9d9d9;
}
img {
  width: 90%;
  margin-left: 5%;
  margin-top: 5%;
}
.bg-secondary {
  background-color: #d9d9d9 !important;
}
</style>
