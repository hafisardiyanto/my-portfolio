<template>
  <div class="app">
    <!-- Navbar -->
    <header class="navbar">
      <div class="logo">Hafis Ardiyanto</div>
      <nav>
        <a
          href="/home"
          :class="{ active: activeSection === 'home' }"
          @click.prevent="setSection('home')"
        >
          Home
        </a>
        <a
          href="/about"
          :class="{ active: activeSection === 'about' }"
          @click.prevent="setSection('about')"
        >
          Tentang
        </a>
        <a
          href="/skills"
          :class="{ active: activeSection === 'skills' }"
          @click.prevent="setSection('skills')"
        >
          Skill
        </a>
        <a
          href="/projects"
          :class="{ active: activeSection === 'projects' }"
          @click.prevent="setSection('projects')"
        >
          Project
        </a>
        <a
          href="/education"
          :class="{ active: activeSection === 'education' }"
          @click.prevent="setSection('education')"
        >
          Pendidikan
        </a>
        <a
          href="/contact"
          :class="{ active: activeSection === 'contact' }"
          @click.prevent="setSection('contact')"
        >
          Kontak
        </a>
      </nav>
    </header>

    <!-- Hero / Home -->
    <section v-if="activeSection === 'home'" id="home" class="hero">
      <!-- FOTO DI SINI -->
      <div class="hero-photo-wrapper">
        <img :src="hafisPhoto" alt="Foto Hafis Ardiyanto" class="hero-photo" />
      </div>

      <h1>Halo, saya <span class="highlight">Hafis Ardiyanto</span></h1>
      <h2>Fresh Graduate D3 Teknologi Informasi</h2>
      <p class="hero-desc">
        Saya merupakan lulusan D3 Teknologi Informasi yang memiliki pengalaman sebagai System Implementor dan System Analyst pada perusahaan pengembang software. Selama bekerja saya terlibat dalam analisis kebutuhan sistem, implementasi aplikasi, pengujian fitur, penyusunan dokumentasi, serta koordinasi dengan tim developer untuk memastikan aplikasi berjalan sesuai kebutuhan bisnis. Pengalaman tersebut membuat saya memahami proses pengembangan perangkat lunak secara menyeluruh. Saya menjadi freelance programmer & pernah membantu mengembangkan beberapa proyek milik mahasiswa, adalah pribadi yang disiplin, mudah beradaptasi, memiliki kemampuan analitis yang baik, dan selalu berusaha memberikan hasil kerja yang berkualitas melalui pembelajaran yang berkelanjutan.
      </p>

      <div class="hero-actions">
        <button @click="setSection('projects')" class="btn-primary">
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

    <!-- Tentang Saya -->
    <!-- Tentang Saya / Resume -->
    <section v-if="activeSection === 'about'" id="about" class="section">
      <div class="about-header">
        <h2>Profil & Pengalaman</h2>
        <p class="about-intro">
          Fresh Graduate D3 Teknologi Informasi dengan pengalaman sebagai System Implementor dan Junior Programmer. Memiliki pengalaman dalam pengembangan aplikasi berbasis web menggunakan Laravel serta implementasi sistem di lingkungan client. Terbiasa melakukan analisis kebutuhan, pengujian sistem, serta pelatihan pengguna. Memiliki ketertarikan pada pengembangan sistem logistik dan solusi berbasis teknologi yang efisien.
        </p>
      </div>

      <div class="resume-grid">
        <div class="resume-column">
          <h3 class="resume-title">Pengalaman Kerja</h3>
          <div class="timeline">
            <!-- Experience 1 -->
            <div class="timeline-item">
              <div class="timeline-dot"></div>
              <div class="timeline-date">2025 – Now</div>
              <h4 class="timeline-company">CV PilarMedia Indonesia</h4>
              <h5 class="timeline-role">System Implementor / System Analyst</h5>
              <ul class="timeline-desc">
                <li>Memulai sebagai QA System pada aplikasi Solog versi 3, melakukan testing, validasi sistem, dan identifikasi bug.</li>
                <li>Berperan sebagai Implementor untuk solog versi 2, melakukan implementasi & training user.</li>
                <li>Melakukan analisa kebutuhan system berdasarkan proses bisnis client.</li>
                <li>Berkontribusi dalam peningkatan system dari hasil testing & feedback lapangan.</li>
                <li>Bertanggung jawab dalam pembangunan aplikasi SaaS logistik (Sendpick) dari tahap awal.</li>
                <li>Melakukan analisis sistem dan memberikan dukungan teknis untuk sistem logistik Solog.</li>
              </ul>
            </div>
            
            <!-- Experience 2 -->
            <div class="timeline-item">
              <div class="timeline-dot"></div>
              <div class="timeline-date">2022 – 2022</div>
              <h4 class="timeline-company">Kopi Kota/Jagadjawi</h4>
              <h5 class="timeline-role">Crew Outlet dan Cashier</h5>
              <ul class="timeline-desc">
                <li>Memberikan pelayanan pelanggan dengan cepat.</li>
                <li>Menjaga kualitas produk sesuai standar outlet.</li>
                <li>Menangani transaksi pembayaran sebagai kasir dengan teliti.</li>
                <li>Mendukung operasional tim untuk menjaga kepuasan pelanggan.</li>
              </ul>
            </div>
          </div>
        </div>

        <div class="resume-column">
          <h3 class="resume-title">Sertifikasi</h3>
          <div class="certification-card">
            <h4>Junior Web Developer - BNSP</h4>
            <p class="cert-cred"><strong>Credential ID:</strong> TIK 1565 40053 2025</p>
            <a href="https://drive.google.com/drive/u/0/folders/13CM96KFQwoklEnhMkQ-N4D7-54EYiyhU" target="_blank" class="cert-link">Lihat Sertifikat</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Skill -->
    <section v-if="activeSection === 'skills'" id="skills" class="section">
      <div class="skills-header">
        <h2>Kemampuan Teknis</h2>
        <p class="section-subtitle">
          Keahlian teknis dan alat pengembangan yang biasa saya gunakan.
        </p>
      </div>

      <div class="skills-grid">
        <div class="skills-card">
          <h3>Technical Skills</h3>
          <ul class="skills-list">
            <li v-for="skill in technicalSkills" :key="skill">{{ skill }}</li>
          </ul>
        </div>

        <div class="skills-card">
          <h3>Tools & Technologies</h3>
          <ul class="skills-list">
            <li v-for="tool in toolsAndTech" :key="tool">{{ tool }}</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Project -->
    <section v-if="activeSection === 'projects'" id="projects" class="section">
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

    <!-- Pendidikan -->
    <section v-if="activeSection === 'education'" id="education" class="section">
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
    <section v-if="activeSection === 'contact'" id="contact" class="section">
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
    <footer class="footer">© {{ new Date().getFullYear() }} Hafis Ardiyanto</footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

/*
  Pastikan file-file ini ada di:
  src/assets/Hafis.jpg
  src/assets/CV_Hafis_Ardiyanto.pdf
*/
import hafisPhoto from "./assets/Hafis.jpg";
import cvPdf from "./assets/CV_Hafis_Ardiyanto.pdf";

const activeSection = ref("home");

const setSection = (section) => { 
  activeSection.value = section;
  window.history.pushState(null, '', '/' + section);
};

onMounted(() => {
  const path = window.location.pathname.replace('/', '');
  const validSections = ['home', 'about', 'skills', 'projects', 'education', 'contact'];
  
  if (validSections.includes(path)) {
    activeSection.value = path;
  } else if (path === '') {
    window.history.replaceState(null, '', '/home');
  }

  window.addEventListener('popstate', () => {
    const currentPath = window.location.pathname.replace('/', '');
    if (validSections.includes(currentPath)) {
      activeSection.value = currentPath;
    } else {
      activeSection.value = 'home';
    }
  });
});

const technicalSkills = [
  "System Analysis",
  "Qa Testing",
  "Client Support & Training",
  "Problem Solving",
  "Technical Documentation",
  "Laravel",
  "vue.js/react",
  "MySQL",
  "Rest API Development"
];

const toolsAndTech = [
  "Git/Github",
  "DBeaver",
  "Laragon",
  "AI-assisted Development (Antigravity, ChatGPT, dll)"
];

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
