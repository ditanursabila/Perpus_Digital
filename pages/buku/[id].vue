<script setup>
useHead({
  title: "Perpus Detail",
  meta: [
    {
      name: "description",
      content: "Book Detail",
    },
  ],
});
const supabase = useSupabaseClient();
const route = useRoute();
const buku = ref([]);
const loading = ref(true);

const getBookById = async () => {
  const { data } = await supabase.from("buku").select(`*, kategori(*), rak(*), judul, penulis, penerbit,tahun_terbit, jml_hal, deskripsi,cover`).eq("id", route.params.id);
  if (data) {
  }
  buku.value = data[0];
  loading.value = false;
};
onMounted(() => {
  getBookById();
});
</script>

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
        <div class="col-lg-2">
          <span v-if="loading">Sedang memuat gambar...</span>
          <span v-else><img :src="buku.cover" alt="cover" class="cover" /></span>
        </div>

        <div class="col">
          <div class="mb-5">
            <div v-if="loading">Sedang memuat data...</div>
            <div v-else>
              <h6>No rak: {{ buku.rak.no_rak }}</h6>
              <h6>Kategori: {{ buku.kategori.nama }}</h6>
              <h6>Judul: {{ buku.judul }}</h6>
              <h6>Penulis: {{ buku.penulis }}</h6>
              <h6>Penerbit: {{ buku.penerbit }}</h6>
              <h6>Tahun terbit: {{ buku.tahun_terbit }} 2019</h6>
              <h6>Jumlah hal: {{ buku.jml_hal }}</h6>
              <h6>Sinopsis/deskripsi:</h6>
              <p>
                {{ buku.deskripsi }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 230px;
}
.cover {
  width: 200px;
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
