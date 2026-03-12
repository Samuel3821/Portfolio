<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<template>
  <section class="about-scroll">
    <div class="about-details">
        <h2 class="details-title">{{ msg }}</h2>
        <p>
          Jeune diplome d'un Bachelor en informatique de gestion a la HEG, je m'interesse
          particulierement au developpement d'applications et a la gestion des donnees.
        </p>
        <p>
          Durant mes etudes, j'ai travaille sur plusieurs projets pratiques utilisant des
          technologies comme SQL / Oracle, PL/SQL, React et Visual Studio. Ces experiences m'ont
          permis de developper des competences en programmation, en conception de bases de donnees
          et en resolution de problemes techniques.
        </p>
        <p>
          J'ai egalement acquis des competences en gestion de projet, notamment en tant que
          Business Analyst, avec des methodes Scrum et agiles, pour comprendre les besoins
          utilisateurs, rediger des user stories et suivre le deploiement de solutions numeriques.
        </p>
        <p>
          Curieux et motive, j'aime comprendre le fonctionnement des systemes informatiques et
          developper des solutions concretes. Je realise regulierement des projets personnels pour
          explorer de nouvelles technologies et renforcer mes competences.
        </p>
        <div class="cv-wrap">
          <a class="cv-link" href="/mon-document.pdf" download="titre-du-fichier.pdf">Mon CV</a>
        </div>
    </div>
  </section>
</template>

<style scoped>
.about-scroll {
  width: min(960px, 100%);
}

.cv-wrap {
  margin-top: 0.5rem;
  text-align: center;
}

.cv-link {
  display: inline-block;
  padding: 0.45rem 0.95rem;
  border-radius: 14px;
  border: 1px solid rgba(255, 255, 255, 0.4);
  background-color: rgba(255, 255, 255, 0.08);
  color: #fff;
  text-decoration: none;
  font-weight: 600;
  transition: background-color 0.25s ease, transform 0.25s ease, border-color 0.25s ease;
}

.cv-link:hover {
  background-color: rgba(255, 255, 255, 0.16);
  border-color: rgba(255, 255, 255, 0.6);
  transform: translateY(-1px);
}

.about-details {
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
}

.about-details:hover {
  border-color: rgba(255, 255, 255, 0.35);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.22);
}

.about-details p {
  margin: 0 0 1rem;
}

.details-title {
  margin: 0 0 1rem;
  font-size: clamp(2rem, 4.5vw, 3.2rem);
  text-align: center;
}

.about-details p:last-child {
  margin-bottom: 0;
}

@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(16px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 768px) {
  .about-details {
    font-size: 1rem;
  }
}
</style>
