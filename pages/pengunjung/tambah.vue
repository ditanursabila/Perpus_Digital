<script setup>
const supabase = useSupabaseClient();

const members = ref([]);
const objectives = ref([]);
const keyword = ref([]);

const form = ref({
  nama: "",
  keanggotaan: "",
  tingkat: "",
  jurusan: "",
  keperluan: "",
});

const kirimData = async () => {
  // console.log(form.value);
  const { error } = await supabase.from("pengunjung").insert([form.value]);
  if (!error) navigateTo("/pengunjung");
};

const getKeanggotaan = async () => {
  const { data, error } = await supabase.from("keanggotaan").select("*");
  if (data) members.value = data;
};
const getKeperluan = async () => {
  const { data, error } = await supabase.from("keperluan").select("*");
  if (data) objectives.value = data;
};

onMounted(() => {
  getKeanggotaan();
  getKeperluan();
});
</script>
<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-1">
        <NuxtLink to="/" class="btn btn-primary mt-3">⬅️Back</NuxtLink>
      </div>
      <div class="col-lg-10">
        <h2 class="text-center mb-4 mt-3 fw-bold">ISI BUKU KUNJUNGAN</h2>

        <form @submit.prevent="kirimData">
          <div class="mb-3">
            <input v-model="form.nama" type="text" class="form-control form-control-lg rounded-5" placeholder="Nama" />
          </div>
          <div class="mb-3">
            <select v-model="form.keanggotaan" class="form-control form-control-lg form-select rounded-5 mb-2">
              <option value="">KEANGGOTAAN</option>
              <option v-for="(member, i) in members" :key="i" :value="member.id">{{ member.nama }}</option>
            </select>
          </div>

          <div class="mb" v-if="form.keanggotaan == '1'">
            <div class="row">
              <div class="col-md-6">
                <select v-model="form.tingkat" class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">TINGKAT</option>
                  <option value="X">X</option>
                  <option value="XI">XI</option>
                  <option value="XII">XII</option>
                </select>
              </div>
              <div class="col-md-6">
                <select v-model="form.jurusan" class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">JURUSAN & KELAS</option>
                  <option value="PPLG 1">PPLG 1</option>
                  <option value="PPLG 2">PPLG 2</option>
                  <option value="PPLG 3">PPLG 3</option>
                  <option value="PPLG 4">PPLG 4</option>
                  <option value="TJKT 1">TJKT 1</option>
                  <option value="TJKT 2">TJKT 2</option>
                  <option value="TJKT 3">TJKT 3</option>
                  <option value="TJKT 4">TJKT 4</option>
                  <option value="TBSM 1">TBSM 1</option>
                  <option value="TBSM 2">TBSM 2</option>
                  <option value="TBSM 3">TBSM 3</option>
                  <option value="TBSM 4">TBSM 4</option>
                  <option value="DKV 1">DKV 1</option>
                  <option value="DKV 2">DKV 2</option>
                  <option value="TOI 1">TOI 1</option>
                  <option value="TOI 2">TOI 2</option>
                </select>
              </div>
            </div>
          </div>

          <div class="mb-3">
            <select v-model="form.keperluan" class="form-control form-control-lg form-select rounded-5 mb-2">
              <option value="">KEPERLUAN</option>
              <option v-for="(item, i) in objectives" :key="i" :value="item.id">{{ item.nama }}</option>
            </select>
          </div>
          <div class="col-lg-12">
            <button type="submit" class="btn btn-primary text-light fw-bold btn-md rounded-3 px-4 border-primary">KIRIM</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 205px;
}
</style>
