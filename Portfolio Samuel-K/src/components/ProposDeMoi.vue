<script setup lang="ts">
import iconProposDeMoi from './icons/IconProposDeMoi.jpg'
import cvSamuelKappel from './CV/CV_Samuel_Kappel.pdf'

defineProps<{
  msg: string
}>()
</script>

<template>
  <section class="about-scroll">
    <div class="about-details">
        <div class="details-header">
          <img :src="iconProposDeMoi" alt="AProposDeMoi" class="details-icon">
          <h2 class="details-title">{{ msg }}</h2>
        </div>

        <p>
          Jeune diplômé d'un Bachelor en informatique de gestion à la HEG, 
          je m'intéresse particulièrement au développement d'applications et à la gestion des données.
        </p>
        <p>
          Durant mes études, j'ai travaillé sur plusieurs projets pratiques utilisant des technologies comme 
          SQL / Oracle, PL/SQL, React et Visual Studio. Ces expériences m'ont permis de développer des compétences en 
          programmation, 
          en conception de bases de données et en résolution de problèmes techniques.
        </p>
        <p>
          J'ai également acquis des compétences en gestion de projet, notamment en tant que Business Analyst, 
          avec des méthodes Scrum et agiles, pour comprendre les besoins utilisateurs, 
          rédiger des user stories et suivre le déploiement de solutions numériques.
        </p>
        <p>
          Curieux et motivé, j'aime comprendre le fonctionnement des systèmes informatiques et 
          développer des solutions concrètes. Je réalise régulièrement des projets personnels 
          pour explorer de nouvelles technologies et renforcer mes compétences.
        </p>
        <div class="cv-wrap">
          <a class="cv-link" :href="cvSamuelKappel" download="CV_Samuel_Kappel.pdf">Mon CV</a>
        </div>
    </div>
  </section>
</template>

<style scoped>
/*mettre un scroll sur la section a propos de moi */
.about-scroll {
  width: min(960px, 100%);
}
/*modification style cv */
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
/* toute la section  */
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
.details-header {
  display: flex;
  align-items: center;
  gap: 0.85rem;
  justify-content: center;
  margin: 0 0 1rem;
}

.details-icon {
  width: 72px;
  height: 72px;
  object-fit:contain;
  border-radius: 50%;
  flex: 0 0 auto;
}

.details-title {
  margin: 0;
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

  .details-header {
    gap: 0.65rem;
  }

  .details-icon {
    width: 56px;
    height: 56px;
  }
}
</style>
