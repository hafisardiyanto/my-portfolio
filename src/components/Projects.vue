<template>
  <section id="projects" class="section">
    <h2>Project</h2>
    <div class="project-list">
      <article class="project-card" v-for="project in projects" :key="project.title">
        <h3>{{ project.title }}</h3>
        <p class="project-role"><strong>Peran:</strong> {{ project.role }}</p>
        <p>{{ project.description }}</p>
        <div v-if="project.credentials" class="demo-credentials" style="margin-top: 10px; font-size: 0.9em;">
          <strong>Demo Login ({{ project.credentials.role }}):</strong>
          <ul style="margin: 5px 0 10px 20px; padding: 0;">
            <li>Email: <code>{{ project.credentials.email }}</code></li>
            <li>Password: <code>{{ project.credentials.password }}</code></li>
          </ul>
        </div>
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
      "Mengembangkan aplikasi sistem absensi karyawan terintegrasi yang mencatat kehadiran (masuk/pulang) secara akurat memvalidasi berdasarkan koordinat lokasi (geolokasi radius) dan batasan waktu nyata (real-time). Fitur Utama: Autentikasi/Login multi-user (Admin & Pegawai), presensi menggunakan geolocation pemetaan, serta modul dasbor admin untuk manajemen pengguna, jam kerja, dan pelaporan (termasuk export rekapan ke Excel).",
    tech: "Laravel, MySQL, Bootstrap, JavaScript",
    links: { demo: "http://43.133.157.230:8084", },
    credentials: { role: "Admin", email: "admin@gmail.com", password: "adminpresensi" }
  },
  {
    title: "Warehouse Management Stok",
    role: "Fullstack Developper",
    description:
      "Aplikasi web untuk mengelola produk,pencatatan stok & dengan aplikasi sederhana.",
    tech: "Laravel,CSS,Bootstrap",
    links: { demo: "http://43.133.157.230:8082" },
    credentials: { role: "Admin", email: "admin@gmail.com", password: "admin123" }
  },
   {
    title: "Aplikasi Kasir",
    role: "Fullstack developper",
    description: "Aplikasi Web Untuk gudang mulai dari pencatatan stok gudang,nama supplier barang/item,Metode pembayaran,bisa menambahkan pegawai(kasir) serta login pegawai(kasir),absen pegawai(kasir),Transaksi Kasir,laporan Penjualan,Dashboard" ,
    tech: "Laravel 11, MySQL, PHP 8.2, Bootstrap 5, JavaScript (jQuery), Blade, Docker, Nginx",
    links: { demo: "http://43.133.157.230:8080/login" },
    credentials: { role: "Owner", email: "superadmin@example.com", password: "admin123" }
   },
   {
    title: "Aplikasi Booking Rental Mobil",
    role: "Fullstack Developer",
    description: "Aplikasi penyewaan/booking mobil berbasis web yang dilengkapi dengan otomatisasi fitur notifikasi WhatsApp menggunakan API Foonte (Fontee) dan notifikasi Email menggunakan SMTP.",
    tech: "Laravel, MySQL, Bootstrap,JavaScript",
    links: { demo: "http://43.133.157.230:8088" },
    credentials: { role: "Admin", email: "admin@rentalmobil.com", password: "admin123" }
   },
   {
    title: "Logistics Boilerplate",
    role: "Fullstack Developer",
    description: "Mengembangkan sistem boilerplate komprehensif untuk order management dan operasional logistik. Membangun RESTful API di sisi backend dengan autentikasi berbasis JWT, fungsionalitas Role-Based Access Control (RBAC) dinamis untuk manajemen hak akses per divisi/modul, serta integrasi database yang solid menggunakan Prisma ORM. Mengimplementasikan antarmuka frontend yang responsif untuk mengelola Master Data dan transaksi operasional, serta mendokumentasikan keseluruhan deployment menggunakan kontainerisasi.",
    tech: "Node.js & Express.js, Prisma ORM, MySQL, Vue.js & Vite, JSON Web Token (JWT), Docker & Podman, Git & RESTful API",
    links: { demo: "http://43.133.157.230:8093/" },
    credentials: { role: "Super Admin", email: "superadmin@logistics.com", password: "superadmin123" }
   }
];
</script>

<style scoped src="../assets/Projects.css"></style>
