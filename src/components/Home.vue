<template>
  <section id="home" class="hero">
    <!-- FOTO DI SINI -->
    <div class="hero-photo-wrapper">
      <img :src="hafisPhoto" alt="Foto Hafis Ardiyanto" class="hero-photo" />
    </div>

    <h1>Halo, saya <span class="highlight">Hafis Ardiyanto</span></h1>
    <h2>Fresh Graduate D3 Teknologi Informasi</h2>
    <p class="hero-desc">
      Saya merupakan lulusan D3 Teknologi Informasi yang memiliki pengalaman sebagai System Implementor dan System Analyst pada perusahaan pengembang software. Selama bekerja saya terlibat dalam analisis kebutuhan sistem, implementasi aplikasi, pengujian fitur, penyusunan dokumentasi, serta koordinasi dengan tim developer untuk memastikan aplikasi berjalan sesuai kebutuhan bisnis. Pengalaman tersebut membuat saya memahami proses pengembangan perangkat lunak secara menyeluruh. Saya menjadi freelance programmer, adalah pribadi yang disiplin, mudah beradaptasi, memiliki kemampuan analitis yang baik, dan selalu berusaha memberikan hasil kerja yang berkualitas melalui pembelajaran yang berkelanjutan.
    </p>

    <div class="hero-actions">
      <button @click="$emit('nav', 'projects')" class="btn-primary">
        Lihat Project Saya
      </button>

      <!-- Tombol CV: buka PDF di tab baru dan juga bisa didownload -->
      <a
        :href="cvPdf"
        target="_blank"
        rel="noopener noreferrer"
        class="btn-secondary"
        download
      >
        Unduh / Lihat CV
      </a>
    </div>
  </section>
</template>

<script setup>
import hafisPhoto from "../assets/Hafis.jpg";
import cvPdf from "../assets/CV_Hafis_Ardiyanto.pdf";

defineEmits(['nav']);
</script>

<style scoped src="../assets/Home.css"></style>
