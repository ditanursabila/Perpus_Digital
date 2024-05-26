<script setup>
useHead({
  title: "Perpus Riwayat",
  meta: [
    {
      name: "description",
      content: "Riwayat Kunjungan",
    },
  ],
});
const supabase = useSupabaseClient();
const visitors = ref([]);
const jmlPengunjung = ref(0);
const keyword = ref([]);

const getJmlPengunjung = async () => {
  const { data, count } = await supabase.from("allpengunjung").select("*", { count: "exact" });
  if (data) jmlPengunjung.value = count;
};

const getPengunjung = async () => {
  const { data } = await supabase.from("allpengunjung").select("*").order("id", { ascending: false }).ilike("nama", `%${keyword.value}%`);
  if (data) visitors.value = data;
};
onMounted(() => {
  getPengunjung();
  getJmlPengunjung();
});
</script>
<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-1">
        <NuxtLink to="/pengunjung/tambah" class="btn btn-primary mt-3">⬅️Back</NuxtLink>
      </div>
      <div class="col-lg-10">
        <h2 class="text-center mb-4 mt-3 fw-bold">RIWAYAT KUNJUNGAN</h2>
        <div class="my-3">
          <form @submit.prevent="getPengunjung">
            <input v-model="keyword" type="search" class="form-control form-control-lg rounded-5 border-primary bg-secondary" placeholder="Cari nama kamu disini..." />
          </form>
        </div>
        <div class="my-3 text-muted">Menampilkan {{ visitors.length }} dari {{ jmlPengunjung }}</div>

        <table class="table table-bordered border-dark table-hover">
          <thead class="fw-bold table-dark">
            <tr>
              <td>NO</td>
              <td>NAMA</td>
              <td>KEANGGOTAAN</td>
              <td>KELAS</td>
              <td>WAKTU</td>
              <td>KEPERLUAN</td>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(visitor, i) in visitors" :key="i">
              <td>{{ i + 1 }}.</td>
              <td>{{ visitor.nama }}</td>
              <td>{{ visitor.keanggotaan.nama }}</td>
              <td>{{ visitor.tingkat }} {{ visitor.jurusan }}</td>
              <td>{{ visitor.tanggal }}, {{ visitor.time }}</td>
              <td v-if="visitor.keperluan != null">
                {{ visitor.keperluan.nama }}
              </td>
              <td v-else="visitor.keperluan == null" class="text-muted">Tidak ada</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 230px;
}
.bg-secondary {
  background-color: #d9d9d9 !important;
}
</style>
