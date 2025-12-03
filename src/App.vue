<template>
  <div class="app">
    <!-- Navbar -->
    <header class="navbar">
      <div class="logo">Hafis Ardiyanto</div>
      <nav>
        <a href="#home">Home</a>
        <a href="#about">Tentang</a>
        <a href="#skills">Skill</a>
        <a href="#projects">Project</a>
        <a href="#education">Pendidikan</a>
        <a href="#contact">Kontak</a>
      </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
      <h1>Halo, saya <span class="highlight">Hafis Ardiyanto</span></h1>
      <h2>Fresh Graduate D3 Teknologi Informasi</h2>
      <p>
        Tertarik pada <strong>Web Development</strong> dengan fokus pada
        <strong>Vue.js</strong> dan pengembangan aplikasi berbasis web.
      </p>
      <button @click="scrollToSection('projects')" class="btn-primary">
        Lihat Project Saya
      </button>
    </section>

    <!-- Tentang Saya -->
    <section id="about" class="section">
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
    <section id="skills" class="section">
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
    <section id="projects" class="section">
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
    <section id="education" class="section">
      <h2>Pendidikan</h2>
      <div class="education-card">
        <h3><strong>SD:</strong>SDN 4 GRESIK</h3>
        <p><strong>Tahun:</strong>2010 - 2016 </p>
        <h3><strong>Sekolah:</strong>SMP 2 KEBOMAS GRESIK</h3>
        <p><strong>Tahun:</strong>2016 - 2019 </p>
        <h3><strong>Jurusan:</strong>(Rekayasa Perangkat Lunak)</h3>
        <p><strong >SMK:</strong>SMK SEMEN GRESIK</p>
        <P><strong>Tahun:</strong>2019 - 2022 </P>
        <h3><strong>Prodi:</strong> Teknologi Informasi</h3>
        <p><strong>Kampus:</strong> POLTEKSI(Politeknik Semen Indonesia) </p>

        <p><strong>Tahun:</strong> 2022 – 2025 </p>
      </div>
    </section>

    <!-- Kontak -->
    <section id="contact" class="section">
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

const scrollToSection = (id) => {
  const el = document.getElementById(id);
  if (el) {
    el.scrollIntoView({ behavior: "smooth" });
  }
};
</script>
