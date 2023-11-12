<template>
  <HeaderComponent/>
    <router-view />
  <FooterView/>
</template>

<script setup>
import HeaderComponent from './components/HeaderComponent.vue';
import FooterView from './components/FooterView.vue';
</script>

