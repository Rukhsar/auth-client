<template>
  <div>
    <div id="nav">
      <TheNavigation />
    </div>
    <main class="py-4">
      <router-view />
    </main>
  </div>
</template>
<script>
import TheNavigation from "@/components/TheNavigation";

export default {
  components: {
    TheNavigation
  }
};
</script>
