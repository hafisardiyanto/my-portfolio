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

    <Home v-if="activeSection === 'home'" @nav="setSection" />
    <About v-if="activeSection === 'about'" />
    <Skills v-if="activeSection === 'skills'" />
    <Projects v-if="activeSection === 'projects'" />
    <Education v-if="activeSection === 'education'" />
    <Contact v-if="activeSection === 'contact'" />

    <!-- Footer -->
    <footer class="footer">© {{ new Date().getFullYear() }} Hafis Ardiyanto</footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";
import Education from "./components/Education.vue";
import Contact from "./components/Contact.vue";

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
</script>
