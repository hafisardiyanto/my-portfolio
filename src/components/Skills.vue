<template>
  <section id="skills" class="section">
    <div class="skills-header">
      <h2>Kemampuan Teknis</h2>
      <p class="section-subtitle">
        Keahlian teknis dan alat pengembangan yang biasa saya gunakan.
      </p>
    </div>

    <div class="skills-grid">
      <div class="skills-card" v-for="category in skillCategories" :key="category.title">
        <h3>{{ category.title }}</h3>
        <ul class="skills-list">
          <li v-for="item in category.items" :key="item">{{ item }}</li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
const skillCategories = [
  {
    title: "Languages",
    items: ["PHP", "JavaScript", "SQL"]
  },
  {
    title: "Frontend",
    items: ["Vue.js", "React.js (Basic)"]
  },
  {
    title: "Backend",
    items: ["Laravel", "Node.js", "Express.js,REST API Development,JWT Authentication"]
  },
  {
    title: "Database & ORM",
    items: ["MySQL", "PostgreSQL", "Prisma ORM", "Eloquent ORM"]
  },
  {
    title: "DevOps & Tools",
    items: [
      "Docker",
      "Podman",
      "Nginx",
      "Ubuntu VPS",
      "Git & GitHub",
      "Postman",
      "Docker Compose",
      "DBeaver"
    ]
  },
  {
    title: "System Analysis & QA",
    items: [
      "System Analysis",
      "QA Testing",
      "Requirement Analysis",
      "Technical Documentation",
      "Client Support & Training"
    ]
  }
];
</script>

<style scoped src="../assets/Skills.css"></style>
