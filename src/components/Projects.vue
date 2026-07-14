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
    title: "Warehouse Management System",
    role: "Fullstack Developper",
    description:
      "Aplikasi web untuk mengelola produk, stok, dan transaksi penjualan dengan tampilan yang sederhana dan responsif.",
    tech: "Vue.js, REST API Laravel, Axios, CSS",
    links: { demo: "", github: "" },
  },
  {
    title: "Website Portofolio Pribadi",
    role: "Fullstack",
    description:
      "Website satu halaman untuk menampilkan profil, keahlian, dan project pribadi sebagai fresh graduate Teknologi Informasi.",
    tech: "Vue.js, HTML, CSS",
    links: { demo: "", github: "" },
  },
];
</script>

<style scoped src="../assets/Projects.css"></style>
