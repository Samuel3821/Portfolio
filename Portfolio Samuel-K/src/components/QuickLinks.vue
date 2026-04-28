<template>
  <section class="quick-links" aria-label="Liens rapides">
    <h2>Mes liens</h2>

    <div class="links-grid">
      <a
        class="link-card"
        href="https://www.linkedin.com/in/samuel-kappel/"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="Voir mon profil LinkedIn"
      >
        <span class="icon" aria-hidden="true">
          <svg viewBox="0 0 24 24" role="img" focusable="false">
            <!-- path qui dessine le logo de LinkedIn -->
            <path
              d="M4.98 3.5C4.98 4.88 3.87 6 2.5 6S0 4.88 0 3.5 1.11 1 2.5 1 4.98 2.12 4.98 3.5zM.5 8h4V23h-4V8zM8 8h3.8v2h.1c.53-1 1.83-2 3.77-2 4.03 0 4.77 2.65 4.77 6.1V23h-4v-7.8c0-1.86-.03-4.26-2.6-4.26-2.6 0-3 2.03-3 4.13V23H8V8z"
            />
          </svg>
        </span>
        <span class="text">
          <strong>LinkedIn</strong>
          <small>Réseau professionnel</small>
        </span>
      </a>

      <a
        class="link-card"
        href="https://github.com/Samuel3821?tab=repositories"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="Voir mon profil GitHub"
      >
        <span class="icon" aria-hidden="true">
          <svg viewBox="0 0 24 24" role="img" focusable="false">
            <!-- path qui dessine le logo de GitHub -->
            <path
              d="M12 .5C5.65.5.5 5.66.5 12.03c0 5.1 3.3 9.42 7.88 10.95.58.11.79-.25.79-.56v-2.17c-3.2.7-3.88-1.54-3.88-1.54-.52-1.34-1.28-1.7-1.28-1.7-1.04-.72.08-.7.08-.7 1.15.08 1.76 1.2 1.76 1.2 1.02 1.78 2.68 1.26 3.34.96.1-.74.4-1.26.72-1.55-2.55-.3-5.24-1.29-5.24-5.74 0-1.26.45-2.3 1.18-3.11-.12-.3-.51-1.5.11-3.12 0 0 .97-.31 3.18 1.19a10.92 10.92 0 0 1 5.78 0c2.2-1.5 3.17-1.19 3.17-1.19.63 1.62.24 2.82.12 3.12.74.81 1.18 1.85 1.18 3.11 0 4.46-2.7 5.43-5.27 5.73.41.36.78 1.08.78 2.17v3.21c0 .31.21.68.8.56A11.54 11.54 0 0 0 23.5 12.03C23.5 5.66 18.35.5 12 .5z"
            />
          </svg>
        </span>
        <span class="text">
          <strong>GitHub</strong>
          <small>Mes projets de code</small>
        </span>
      </a>
    </div>

    <section class="site-note" aria-label="Site en construction">
      <p>
        Site en construction, n'hésitez pas à me contacter pour en savoir plus sur mon parcours
        et mes projets !
      </p>
    </section>
  </section>
</template>

<style scoped>
.quick-links {
  width: min(980px, 100%);
}

h2 {
  margin-bottom: 1rem;
  font-size: 1.4rem;
  animation: fade-up 0.5s ease both;
}

.links-grid {
  display: grid;
  gap: 0.9rem;
  grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
}

.link-card {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  padding: 0.9rem 1rem;
  border-radius: 12px;
  text-decoration: none;
  color: #fff;
  background-color: rgba(0, 0, 0, 0.35);
  border: 1px solid rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(2px);
  transition: transform 0.25s ease, background-color 0.25s ease, border-color 0.25s ease,
    box-shadow 0.25s ease;
  animation: fade-up 0.55s ease both;
}

.link-card:hover {
  transform: translateY(-1px);
  background-color: rgba(0, 0, 0, 0.45);
  border-color: rgba(255, 255, 255, 0.45);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.22);
}

.link-card:nth-child(1) {
  animation-delay: 0.12s;
}

.link-card:nth-child(2) {
  animation-delay: 0.24s;
}

.icon {
  width: 28px;
  height: 28px;
  display: inline-flex;
}

.icon svg {
  width: 100%;
  height: 100%;
  fill: currentColor;
}

.text {
  display: flex;
  flex-direction: column;
  line-height: 1.2;
}

.text small {
  opacity: 0.85;
}

.site-note {
  width: 100%;
  color: #fff;
  font-size: 1.1rem;
  line-height: 1.7;
  text-align: left;
  animation: fade-up 0.55s ease;
  background-color: rgba(0, 0, 0, 0.34);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 14px;
  padding: 1.1rem 1.2rem;
  transition: border-color 0.25s ease, box-shadow 0.25s ease;
  margin-top: 1.5rem;
}

.site-note p {
  margin: 0;
}

@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(14px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
