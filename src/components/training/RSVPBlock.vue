<template>
  <div>
    <h2 class="mb-2">Coming Soon! – SAF training Fall 2022!</h2>
    <p >
      We’re happy to announce plans to provide training to SAF Users and Developers. 
      These are free, on-line virtual, hands-on, instructor-led 1-2 day classes.
    </p>
    <p >
      Sponsored by MDA, the
      <a :href="communityData.trainingSiteBasic" target="_blank"
        >Beginner Security Automation Developer Class</a
      >
      will again be offered in late Fall (10am-5pm ET both days) (12 CPE). Check back in for more details to come!
    </p>
    <p >
      Sponsored by MDA, the
      <a :href="communityData.trainingSiteAdvanced" target="_blank"
        >follow-on Advanced Security Automation Developer Class</a
      >
      will again be offered in late Fall (10am-5pm ET both days) (12 CPE). Check back in for more details to come!
    </p>
    <!-- <p >
      Please RSVP if you are interested in attending or have additional
      questions. If you are having trouble with the form, please email
      <a :href="'mailto:' + communityData.trainingContactEmail" target="_blank"
        >SAF@groups.mitre.org.</a
      >
    </p> -->
    <!-- <v-btn
      elevation="8"
      large
      outlined
      text
      x-large
      :href="communityData.trainingSignUpLink"
      target="_blank"
      class="ma-8"
      color="accent"
      >RSVP!</v-btn
    > -->
    <p >
      For information on prerequisites and resources for learning Ruby, look at the saf-training material available 
      <a
        href="https://mitre.github.io/saf-training/"
        target="_blank"
        >here</a
      > or
      <a
        href="https://mitre-saf-training.netlify.app/"
        target="_blank"
        >here.</a
      >
    </p>
  </div>
</template>
<script>
  import communityData from "@/assets/data/communityData.json";
  export default {
    data() {
      return {
        communityData: communityData,
      };
    },
  };
</script>
