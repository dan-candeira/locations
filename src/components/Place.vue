<template>
  <img :src="location.img" width="235" height="300" />
  <!-- slots are similar to props.child -->
  <slot></slot>
  <p>{{ location.desc }}</p>
</template>

<script setup>
defineProps({
  location,
});
</script>
