<template>
  <div class="portfolio">
    <overview-component></overview-component>
    <about-component></about-component>
    <projects-component></projects-component>
    <contact-component></contact-component>
    <footer-component></footer-component>
  </div>
</template>

<script>
import AboutComponent from './About';
import ContactComponent from './Contact';
import FooterComponent from './Footer';
import OverviewComponent from './Overview';
import ProjectsComponent from './Projects';

export default {
  name: 'Portfolio',
  components: {
    AboutComponent,
    ContactComponent,
    FooterComponent,
    OverviewComponent,
    ProjectsComponent,
  },
};
</script>
