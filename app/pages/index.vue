<script setup lang="ts">
const projectSections = [
  {
    id: 'bachelors',
    title: 'Bachelor\'s',
    description: 'University-issued projects created to learn and practise standard data science techniques.',
    projects: [
      {
        number: '01',
        title: 'Hotel customer value predictor',
        description: 'Performing regression and classification on a simulated dataset to predict customer value. This project has also been made production-ready with AzureML and Kubernetes.',
        tags: ['Simulated', 'Machine learning'],
        repository: 'https://github.com/williamplancke/mlops-project'
      }
    ]
  },
  {
    id: 'strategy-simulation',
    title: 'Strategy & simulation',
    description: 'Strategy games provide vast simulated environments with rich data covering economies, warfare, populations, and more. Their detail and high-throughput data make them ideal environments for machine learning experiments.',
    projects: [
      {
        number: '01',
        title: 'EU4 Province Value Estimator',
        description: 'Collection of province data from both the EU4 source code and real multiplayer save files to train a regression model on \'province value\' based on player behavior.',
        tags: ['Europa Universalis 4', 'Data cleaning and preprocessing'],
        repository: 'https://github.com/williamplancke/eu4-pve-collection-training'
      }
    ]
  }
]
</script>

<template>
  <div class="site-shell">
    <header class="site-header page-width">
      <a
        class="wordmark"
        href="#top"
        aria-label="William Plancke, back to top"
      >
        WP<span class="wordmark-dot">.</span>
      </a>

      <nav aria-label="Primary navigation">
        <a href="#projects">Projects</a>
      </nav>
    </header>

    <main id="top">
      <section
        class="hero page-width"
        aria-labelledby="page-title"
      >
        <p class="eyebrow">
          AI Student
        </p>
        <h1 id="page-title">
          William<br>
          <span>Plancke</span>
        </h1>
      </section>

      <section
        id="projects"
        class="projects page-width section-grid"
        aria-labelledby="projects-title"
      >
        <h2
          id="projects-title"
          class="section-label"
        >
          01 / Projects
        </h2>
        <div class="section-content">
          <section
            v-for="section in projectSections"
            :key="section.id"
            class="project-group"
            :aria-labelledby="`${section.id}-title`"
          >
            <div class="section-heading">
              <h3 :id="`${section.id}-title`">
                {{ section.title }}
              </h3>
              <p>{{ section.description }}</p>
            </div>

            <div class="project-list">
              <article
                v-for="project in section.projects"
                :key="project.repository || project.title"
                class="project-card"
              >
                <span class="project-number">{{ project.number }}</span>
                <div class="project-details">
                  <h4>{{ project.title }}</h4>
                  <p>{{ project.description }}</p>
                  <ul
                    class="tag-list"
                    :aria-label="`${project.title} technologies`"
                  >
                    <li
                      v-for="tag in project.tags"
                      :key="tag"
                    >
                      {{ tag }}
                    </li>
                  </ul>
                </div>
                <a
                  v-if="project.repository"
                  class="repo-link"
                  :href="project.repository"
                  target="_blank"
                  rel="noreferrer"
                  :aria-label="`Open ${project.title} on GitHub`"
                >
                  GitHub <span aria-hidden="true">↗</span>
                </a>
                <span
                  v-else
                  class="repo-link repo-link--muted"
                >Link soon</span>
              </article>
            </div>
          </section>
        </div>
      </section>
    </main>

    <footer class="site-footer page-width">
      <p>© {{ new Date().getFullYear() }} William Plancke</p>
      <a href="#top">Back to top ↑</a>
    </footer>
  </div>
</template>
