<script setup>
useHead({
  title: "Perpus Home",
  meta: [
    {
      name: "description",
      content: "Home Page",
    },
  ],
});
const visitor = ref(0);
const Hbuku = ref(0);

const getHitung = async () => {
  const { data, count } = await supabase.from("pengunjung").select("*", { count: "exact" });
  if (data) visitor.value = count;
};
const getHbook = async () => {
  const { data, count } = await supabase.from("buku").select("*", { count: "exact" });
  if (data) Hbuku.value = count;
};

onMounted(() => {
  getHitung();
  getHbook();
});
</script>

<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung/tambah">
          <div class="card bg-pengunjung rounded-5 mb-4">
            <div class="card-body">
              <h2 class="pengunjung fw-bold">Pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card bg-buku rounded-5">
            <div class="card-body">
              <h2 class="fw-bold">Cari buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
  <!--STATISTIK-->
  <div class="statistik">
    <h2 class="pt-4 ps-3 fw-bold">STATISTIK</h2>
  </div>
  <!--STATISTIK CARD-->
  <div class="row my-5">
    <div class="col-lg-6">
      <nuxt-link to="/pengunjung">
        <div class="card bg-warning rounded-5 ms-3 mb-4">
          <div class="card-body text">
            <h2 class="ps-5">{{ visitor }}</h2>
            <h3 class="pt-5">Pengunjung</h3>
          </div>
        </div>
      </nuxt-link>
    </div>

    <div class="col-lg-6">
      <div class="card bg-success rounded-5 ms-3">
        <div class="card-body text">
          <h2 class="ps-5">{{ Hbuku }}</h2>
          <h3 class="pt-5">Buku</h3>
        </div>
      </div>
    </div>
  </div>
  <!--STATISTIK DIAGRAM-->
  <div>
    <Chart />
  </div>
</template>

<style scoped>
.card {
  height: 250px;
  box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
  background: url("../assets/img/kunjungan.webp") no-repeat center center;
  background-size: cover;
  color: black;
}
.card.bg-buku {
  background: url("../assets/img/caribuku.webp") no-repeat center center;
  background-size: cover;
  color: black;
}
.bg-warning {
  background-color: #ffec44 !important;
  color: black;
}
.bg-success {
  background-color: #9adf7a !important;
}
.text {
  display: flex;
  align-items: center;
  justify-content: left;
}
.text h2,
h1 {
  font-size: 7rem;
}
.container-fluid {
  margin-top: 220px;
}
</style>
