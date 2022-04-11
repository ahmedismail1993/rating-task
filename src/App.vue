<template>
  <div id="app">
    <Rating />
  </div>
</template>

<script>
export default {
  name: "App",
  components: {
    Rating: () => import("@/components/Rating"),
  },
};
</script>
