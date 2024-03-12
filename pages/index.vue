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
  <div class="statistik rounded-5">
    <h2 class="pt-4 ps-3 fw-bold">STATISTIK</h2>
  </div>
  <!--STATISTIK CARD-->
  <div class="row my-5">
    <div class="col-lg-6">
      <div class="card bg-warning rounded-5 ms-3 mb-4">
        <div class="card-body text">
          <h2 class="ps-5">5</h2>
          <h3 class="pt-5">Pengunjung</h3>
        </div>
      </div>
    </div>
    <div class="col-lg-6">
      <div class="card bg-success rounded-5 ms-3">
        <div class="card-body text">
          <h2 class="ps-5">100</h2>
          <h3 class="pt-5">Buku</h3>
        </div>
      </div>
    </div>
  </div>
  <!--STATISTIK DIAGRAM-->
  <div class="row mt-3">
    <div class="col-sm-9 offset-sm-1">
      <div class="card-body">
        <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
      </div>
    </div>
  </div>
</template>
<script>
import { Bar } from "vue-chartjs";
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from "chart.js";

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale);

export default {
  name: "BarChart",
  components: { Bar },
  data() {
    return {
      chartData: {
        labels: ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"],
        datasets: [
          {
            label: "",
            data: [80, 20, 60, 25, 45, 17, 55, 100, 59, 35, 25, 79],
            backgroundColor: ["#FF0000", "#00008B", "#1B8A6B", "#00008B", "#1B8A6B", "#00008B", "#1B8A6B", "#FF0000", "#1B8A6B", "#1B8A6B", "#00008B", "#FF0000"],
          },
        ],
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        aspectRatio: 0.7,
      },
    };
  },
};
</script>

<style scoped>
.card {
  height: 250px;
  box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
  background: url("../assets/img/kunjungan.png") no-repeat center center;
  background-size: cover;
  color: black;
}
.card.bg-buku {
  background: url("../assets/img/caribuku.png") no-repeat center center;
  background-size: cover;
  color: black;
}
.card-bawah {
  display: flex;
  justify-content: center;
  margin-top: 80px;
}
.bg-warning {
  background-color: #ffec44 !important;
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
