<template>
  <div class="app">
    <!-- Navbar -->
    <header class="navbar">
      <div class="logo">Hafis Ardiyanto</div>
      <nav>
        <a
          href="#"
          :class="{ active: activeSection === 'home' }"
          @click.prevent="setSection('home')"
        >
          Home
        </a>
        <a
          href="#"
          :class="{ active: activeSection === 'about' }"
          @click.prevent="setSection('about')"
        >
          Tentang
        </a>
        <a
          href="#"
          :class="{ active: activeSection === 'skills' }"
          @click.prevent="setSection('skills')"
        >
          Skill
        </a>
        <a
          href="#"
          :class="{ active: activeSection === 'projects' }"
          @click.prevent="setSection('projects')"
        >
          Project
        </a>
        <a
          href="#"
          :class="{ active: activeSection === 'education' }"
          @click.prevent="setSection('education')"
        >
          Pendidikan
        </a>
        <a
          href="#"
          :class="{ active: activeSection === 'contact' }"
          @click.prevent="setSection('contact')"
        >
          Kontak
        </a>
      </nav>
    </header>

    <!-- Hero / Home -->
    <section
      v-if="activeSection === 'home'"
      id="home"
      class="hero"
    >
      <!-- FOTO DI SINI -->
      <div class="hero-photo-wrapper">
        <img
          :src="hafisPhoto"
          alt="Foto Hafis Ardiyanto"
          class="hero-photo"
        />
      </div>

      <h1>Halo, saya <span class="highlight">Hafis Ardiyanto</span></h1>
      <h2>Fresh Graduate D3 Teknologi Informasi</h2>
      <p>
        Tertarik pada <strong>Web Development</strong> dengan fokus pada
        <strong>Vue.js</strong> dan pengembangan aplikasi berbasis web.
      </p>
      <button @click="setSection('projects')" class="btn-primary">
        Lihat Project Saya
      </button>
    </section>

    <!-- Tentang Saya -->
    <section
      v-if="activeSection === 'about'"
      id="about"
      class="section"
    >
      <h2>Tentang Saya</h2>
      <p>
        Saya adalah lulusan D3 Teknologi Informasi yang memiliki ketertarikan
        pada pengembangan aplikasi web. Terbiasa menggunakan HTML, CSS,
        JavaScript, serta framework seperti Vue.js dan Laravel.
      </p>
      <p>
        Saya senang belajar teknologi baru, mengerjakan project, dan terbuka
        terhadap feedback untuk terus berkembang. Saat ini saya sedang mencari
        kesempatan kerja sebagai <strong>Junior Web Developer</strong> atau
        <strong>Frontend Developer</strong>.
      </p>
    </section>

    <!-- Skill -->
    <section
      v-if="activeSection === 'skills'"
      id="skills"
      class="section"
    >
      <h2>Skill</h2>
      <p class="section-subtitle">
        Berikut gambaran level kemampuan saya dalam beberapa teknologi:
      </p>

      <div class="skill-graph">
        <div
          class="skill-graph-item"
          v-for="skill in skillChart"
          :key="skill.name"
        >
          <div class="skill-graph-label">
            <span>{{ skill.name }}</span>
            <span>{{ skill.level }}%</span>
          </div>
          <div class="skill-graph-bar">
            <div
              class="skill-graph-bar-fill"
              :style="{ width: skill.level + '%' }"
            ></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Project -->
    <section
      v-if="activeSection === 'projects'"
      id="projects"
      class="section"
    >
      <h2>Project</h2>
      <div class="project-list">
        <article
          class="project-card"
          v-for="project in projects"
          :key="project.title"
        >
          <h3>{{ project.title }}</h3>
          <p class="project-role"><strong>Peran:</strong> {{ project.role }}</p>
          <p>{{ project.description }}</p>
          <p class="tech-stack">
            <strong>Teknologi:</strong> {{ project.tech }}
          </p>
          <div v-if="project.links" class="project-links">
            <a
              v-if="project.links.demo"
              :href="project.links.demo"
              target="_blank"
            >
              Demo
            </a>
            <a
              v-if="project.links.github"
              :href="project.links.github"
              target="_blank"
            >
              GitHub
            </a>
          </div>
        </article>
      </div>
    </section>

    <!-- Pendidikan -->
    <section
      v-if="activeSection === 'education'"
      id="education"
      class="section"
    >
      <h2>Pendidikan</h2>
      <div class="education-card">
        <h3><strong>SD:</strong> SDN 4 GRESIK</h3>
        <p><strong>Tahun:</strong> 2010 - 2016 </p>
        <h3><strong>Sekolah:</strong> SMP 2 KEBOMAS GRESIK</h3>
        <p><strong>Tahun:</strong> 2016 - 2019 </p>
        <h3><strong>Jurusan:</strong> (Rekayasa Perangkat Lunak)</h3>
        <p><strong>SMK:</strong> SMK SEMEN GRESIK</p>
        <p><strong>Tahun:</strong> 2019 - 2022 </p>
        <h3><strong>Prodi:</strong> Teknologi Informasi</h3>
        <p><strong>Kampus:</strong> POLTEKSI (Politeknik Semen Indonesia)</p>
        <p><strong>Tahun:</strong> 2022 – 2025 </p>
      </div>
    </section>

    <!-- Kontak -->
    <section
      v-if="activeSection === 'contact'"
      id="contact"
      class="section"
    >
      <h2>Kontak</h2>
      <p>Silakan hubungi saya melalui:</p>
      <ul class="contact-list">
        <li><strong>Email:</strong> hafisardiyanto19@gmail.com</li>
        <li><strong>WhatsApp:</strong> 085748174062</li>
        <li><strong>GitHub:</strong> github.com/username</li>
        <li><strong>LinkedIn:</strong> linkedin.com/in/username</li>
      </ul>
    </section>

    <!-- Footer -->
    <footer class="footer">
      © {{ new Date().getFullYear() }} Hafis Ardiyanto · Dibuat dengan Vue.js
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";
// pastikan nama file dan ekstensi SAMA persis dengan yang ada di folder
// misal file: src/assets/Hafis.JPG
import hafisPhoto from "src/assets/Hafis.jpg";

const activeSection = ref("home"); // default tampilan awal: Home

const setSection = (section) => {
  activeSection.value = section;
};

const skillChart = [
  { name: "HTML & CSS", level: 95 },
  { name: "JavaScript", level: 90 },
  { name: "Vue.js", level: 80 },
  { name: "PHP dasar", level: 85 },
  { name: "Laravel dasar", level: 85 },
  { name: "MySQL", level: 80 },
  { name: "Git & GitHub", level: 85 },
];

const projects = [
  {
    title: "Sistem Absensi Karyawan Berbasis Web dengan GPS",
    role: "Fullstack Developer",
    description:
      "Aplikasi absensi yang mencatat kehadiran karyawan berdasarkan lokasi (geolokasi) dan waktu. Memiliki fitur login, absensi, dan laporan sederhana.",
    tech: "Laravel, MySQL, Bootstrap, JavaScript",
    links: {
      demo: "",
      github: "",
    },
  },
  {
    title: "Warehouse Management System",
    role: "Fullstack Developper",
    description:
      "Aplikasi web untuk mengelola produk, stok, dan transaksi penjualan dengan tampilan yang sederhana dan responsif.",
    tech: "Vue.js, REST API Laravel, Axios, CSS",
    links: {
      demo: "",
      github: "",
    },
  },
  {
    title: "Website Portofolio Pribadi",
    role: "Fullstack",
    description:
      "Website satu halaman untuk menampilkan profil, keahlian, dan project pribadi sebagai fresh graduate Teknologi Informasi.",
    tech: "Vue.js, HTML, CSS",
    links: {
      demo: "",
      github: "",
    },
  },
];
</script>
