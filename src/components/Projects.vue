<template>
  <section id="projects" class="section">
    <h2>Project</h2>
    <div class="project-list">
      <article class="project-card" v-for="project in projects" :key="project.title">
        <h3>{{ project.title }}</h3>
        <p class="project-role"><strong>Peran:</strong> {{ project.role }}</p>
        <p>{{ project.description }}</p>
        <p class="tech-stack"><strong>Teknologi:</strong> {{ project.tech }}</p>
        <div v-if="project.links" class="project-links">
          <a v-if="project.links.demo" :href="project.links.demo" target="_blank">Demo</a>
          <a v-if="project.links.github" :href="project.links.github" target="_blank">GitHub</a>
        </div>
      </article>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: "Sistem Absensi Karyawan Berbasis Web dengan GPS",
    role: "Fullstack Developer",
    description:
      "Aplikasi absensi yang mencatat kehadiran karyawan berdasarkan lokasi (geolokasi) dan waktu. Memiliki fitur login, absensi, dan laporan sederhana.",
    tech: "Laravel, MySQL, Bootstrap, JavaScript",
    links: { demo: "", github: "" },
  },
  {
    title: "Warehouse Management Stok",
    role: "Fullstack Developper",
    description:
      "Aplikasi web untuk mengelola produk,pencatatan stok & dengan aplikasi sederhana.",
    tech: "Laravel,CSS,Bootstrap",
    links: { demo: "http://43.133.157.230:8082/login" },
  },
   {
    title: "Aplikasi Kasir",
    role: "Fullstack developper",
    description: "Aplikasi Web Untuk gudang mulai dari pencatatan stok gudang,nama supplier barang/item,Metode pembayaran,bisa menambahkan pegawai(kasir) serta login pegawai(kasir),absen pegawai(kasir),Transaksi Kasir,laporan Penjualan,Dashboard" ,
    tech: "Laravel,CSS & JavaScript",
    links: { demo: "http://43.133.157.230:8080/login" }
   }
];
</script>

<style scoped src="../assets/Projects.css"></style>
