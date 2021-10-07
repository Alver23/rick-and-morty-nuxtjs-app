<template>
  <div class="flex flex-col min-h-screen">
    <Header />
    <main style="min-height: 90vh" class="mb-2">
      <Nuxt />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/header";
import Footer from "@/components/footer";

export default {
  components: {
    Header,
    Footer,
  },
};
</script>
