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
      <div class="col-lg-1">
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
        <div v-if="loading">Sedang memuat data...</div>
        <div v-else>
          <ul class="list-group list-group-flush">
            <li class="list-group-item">No rak: {{ buku.rak.no_rak }}</li>
            <li class="list-group-item">Kategori: {{ buku.kategori.nama }}</li>
            <li class="list-group-item">Judul: {{ buku.judul }}</li>
            <li class="list-group-item">Penulis: {{ buku.penulis }}</li>
            <li class="list-group-item">Penerbit: {{ buku.penerbit }}</li>
            <li class="list-group-item">Tahun terbit: {{ buku.tahun_terbit }}</li>
            <li class="list-group-item">Jumlah hal: {{ buku.jml_hal }}</li>
            <li class="list-group-item">Sinopsis/deskripsi: {{ buku.deskripsi }}</li>
          </ul>
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
