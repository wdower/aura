<template>
  <div>
    <h2 class="mb-2">RSVP – SAF training Fall 2022!</h2>
    <p >
      We’re happy to announce plans to provide training to SAF Users and Developers. 
      These are free, on-line virtual, hands-on, instructor-led 1-2 day classes.
    </p>
    <p >
      Sponsored by DSCA, the new, 
      <a :href="communityData.trainingSiteUser" target="_blank"
        >SAF User Class</a
      >
      will be offered in-person only on September 27, 2022 (9am-4pm) (6 CPE)
    </p>
    <p >
      Sponsored by MDA, the
      <a :href="communityData.trainingSiteBasic" target="_blank"
        >Beginner Security Automation Developer Class</a
      >
      will again be offered in October/November (9am-4pm both days) (12 CPE). Check back in for more details to come!
    </p>
    <p >
      Sponsored by MDA, the
      <a :href="communityData.trainingSiteAdvanced" target="_blank"
        >follow-on Advanced Security Automation Developer Class</a
      >
      will again be offered in October/November (9am-4pm both days) (12 CPE). Check back in for more details to come!
    </p>
    <p >
      Please RSVP if you are interested in attending or have additional
      questions. If you are having trouble with the form, please email
      <a :href="'mailto:' + communityData.trainingContactEmail" target="_blank"
        >SAF@groups.mitre.org.</a
      >
    </p>
    <v-btn
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
    >
    <p >
      A note on prerequisites: For the Beginner Security Automation Developer Class, knowledge of basic
      programming concepts, modern language conventions and some working
      experience with a modern language (e.g., Ruby, Python, Go, etc) is useful.
      (Inspec is a Ruby Domain-specific language (DSL)). To become more familiar
      with Ruby, feel free to review the following Ruby primers. For the
      follow-on advanced class (basic is a preferred prerequisite), we'll be
      writing InSpec Resources in the Ruby language, so it is highly recommended
      students of the advanced class unfamiliar with Ruby review the following
      Ruby primers
      <a
        href="https://www.ruby-lang.org/en/documentation/quickstart/"
        target="_blank"
        >here</a
      >
      and on
      <a
        href="https://www.youtube.com/watch?v=t_ispmWmdjY&vl=en"
        target="_blank"
        >youtube.</a
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
