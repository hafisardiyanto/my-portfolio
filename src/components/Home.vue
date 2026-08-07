<template>
  <section id="home" class="hero">
    <!-- FOTO DI SINI -->
    <div class="hero-photo-wrapper">
      <img :src="hafisPhoto" alt="Foto Hafis Ardiyanto" class="hero-photo" />
    </div>

    <h1>Halo, saya <span class="highlight">Hafis Ardiyanto</span></h1>
    <h2>Fresh Graduate D3 Teknologi Informasi</h2>
    <p class="hero-desc">
      Fresh Graduate D3 Teknologi Informasi dengan pengalaman sebagai System Implementor dan Junior Fullstack Web Developer. Berpengalaman mengembangkan aplikasi web menggunakan Laravel, Vue.js, PostgreSQL, dan REST API, serta implementasi sistem, QA Testing, dan analisis kebutuhan bisnis.
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
import cvPdf from "../assets/Hafis ardiyanto Terbaru.pdf";

defineEmits(['nav']);
</script>

<style scoped src="../assets/Home.css"></style>
