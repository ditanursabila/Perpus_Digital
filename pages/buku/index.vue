<script setup>
useHead({
  title: "Perpus Books",
  meta: [
    {
      name: "description",
      content: "Book Page",
    },
  ],
});

const supabase = useSupabaseClient();
const books = ref([]);
const keyword = ref([]);
const loading = ref(true);
const jmlbuku = ref(0);

const getJmlBooks = async () => {
  const { data, count } = await supabase.from("buku").select("*", { count: "exact" });
  if (data) jmlbuku.value = count;
};
const getBooks = async () => {
  loading.value = true;
  const { data, error } = await supabase
    .from("buku")
    .select(
      `
      id, judul, penulis, penerbit,
      kategori(nama), rak(no_rak),cover
    `
    )
    .ilike("judul", `%${keyword.value}%`);
  if (data) {
    books.value = data;
    loading.value = false;
  }
  if (error) throw error;
};

onMounted(() => {
  getBooks();
  getJmlBooks();
});
</script>

<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-1">
        <NuxtLink to="/" class="btn btn-primary mt-3">⬅️Back</NuxtLink>
      </div>
      <div class="col-lg-10">
        <h2 class="text-center mb-4 mt-3 fw-bold">CARI BUKU</h2>

        <form @submit.prevent="getBooks">
          <input v-model="keyword" class="form-control form-control-lg rounded-pill bg-secondary border-primary" placeholder="Mau baca apa hari ini?" />
        </form>

        <div class="my-3 text-muted">Menampilkan {{ books.length }} dari {{ jmlbuku }}</div>

        <div class="row">
          <div v-if="loading">
            <div class="text-center">
              <button class="btn btn-primary" type="button" disabled>
                <span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span>
                Sedang memuat buku...
              </button>
            </div>
          </div>

          <div v-for="(book, i) in books" :key="i" class="col-sm-2 mb-4 me-4">
            <div class="card">
              <NuxtLink :to="`buku/${book.id}`">
                <img :src="book.cover" class="cover" alt="cover 1" />
              </NuxtLink>
              <div class="card-body">
                <p>{{ book.judul }}</p>
              </div>
            </div>
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
}
img {
  width: 90%;
  margin-left: 5%;
  margin-top: 5%;
}
.bg-secondary {
  background-color: #d9d9d9 !important;
  width: 100%;
}
.border-primary {
  border-color: rgb(122, 122, 179) !important;
}
</style>
