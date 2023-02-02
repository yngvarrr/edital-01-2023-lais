<template>
  <div class="modulos">
    <HeaderMobile />
    <div class="conteudo" :class="{ open: showNav }">
      <div class="barra_sup">
        <div id="navigation" v-if="mobileView" @click="showNav = !showNav">
          <i class="fas fa-bars"></i>
        </div>
        <img :src="require('../assets/logo avasus header.svg')" alt="Logo AVASUS" class="logo__avasus" v-if="mobileView">
        <Header v-if="!mobileView" />
      </div>
      <Pag2 />
      <Footer />
    </div>
  </div>
</template>

<script>
import Pag2 from "@/components/Pag2.vue";
import Header from "@/components/Header.vue";
import HeaderMobile from "@/components/HeaderMobile.vue";
import Footer from "@/components/Footer.vue";

export default {
  data: () => {
    return {
      mobileView: true,
      showNav: false,
    };
  },
  methods: {
    handleView() {
      this.mobileView = window.innerWidth <= 400;
    },
  },
  name: "ModulosAvasus",
  components: {
    Header,
    HeaderMobile,
    Pag2,
    Footer,
  },
  created() {
    this.handleView();
  },
};
</script>

<style scoped>
@import url("https://use.fontawesome.com/releases/v5.9.0/css/all.css");

#navigation {
  padding: 10px 10px 20px;
  margin-right: 10px;
  cursor: pointer;
}

i {
  font-size: 2rem;
}

.barra_sup {
  display: flex;
  width: 100%;
}

.conteudo {
  position: absolute;
  top: 5px;
  width: 100%;
  height: 100%;
  background-color: #fff;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  transition: 1s transform cubic-bezier(0, 0.12, 0.14, 1);
}

.open {
  transform: translateX(300px);
}
</style>
