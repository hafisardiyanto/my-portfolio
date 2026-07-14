<template>
  <section id="skills" class="section">
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
</template>

<script setup>
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
</script>

<style scoped src="../assets/Skills.css"></style>
