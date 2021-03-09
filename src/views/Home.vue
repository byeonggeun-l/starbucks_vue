<template>
  <div class="home">
    <Header />
    <HelloWorld />
    <VisualSection />
    <NoticeSection />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Header from "@/components/Header.vue";
import VisualSection from "@/views/VisualSection.vue";
import NoticeSection from "@/views/NoticeSection.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
    Header,
    VisualSection,
    NoticeSection,
  }
};
</script>
