<template>
  <div class="home">
    <Header />
    <HelloWorld />
    <VisualSection />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Header from "@/components/Header.vue";
import VisualSection from "@/views/VisualSection.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
    Header,
    VisualSection,
  }
};
</script>
