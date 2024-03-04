<template>
  <div class="container-fluid">
    <div class="row">
      <div>
        <NuxtLink to="/" class="btn btn-primary mt-3">⬅️Back to home</NuxtLink>
      </div>
      <div class="col-lg-12">
        <h2 class="text-center my-4">CARI BUKU</h2>
        <div class="my-3">
          <input type="search" class="form-control rounded-5" placeholder="Mau baca apa hari ini?" />
        </div>
        <div class="my-3 text-muted">menampilkan 3 dari 100</div>
        <div class="row">
          <div class="col-sm-2">
            <nuxt-link to="/buku/buku1">
              <div class="card-header">
                <div class="card-body">
                  <img src="~/assets/img/Bincang_Akhlak.jpg" class="img-thumbnail" alt="cover 1" />
                </div>
              </div>
            </nuxt-link>
          </div>
          <div class="col-sm-2">
            <nuxt-link to="/buku/buku-2">
              <div class="card-header">
                <div class="card-body">
                  <img src="~/assets/img/candy.jpg" class="img-thumbnail" alt="cover 2" />
                </div>
              </div>
            </nuxt-link>
          </div>
          <div class="col-sm-2">
            <nuxt-link to="/buku/buku_3">
              <div class="card-header">
                <div class="card-body">
                  <img src="~/assets/img/Bleeding.jpg" class="img-thumbnail" alt="cover 3" />
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
}
.img-thumbnail {
  width: 80%;
}
</style>
