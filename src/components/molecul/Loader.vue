<!-- Loader.vue -->
<template>
  <div class="card shadow m-3">
    <div class="loader">
      <span class="loading-text">Loading...</span>
    </div>
  </div>
</template>

<style scoped>
.card {
  /* Feel free to adjust these styles based on your design preference */
  height: 150px;
  margin: auto;
  border-radius: 8px;
  background: #fff;
}

.shadow {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1), 0 6px 20px rgba(0, 0, 0, 0.07);
}

.loader {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

.loading-text {
  font-size: 1.5rem;
  animation: fadeInOut 1.5s infinite;
}

@keyframes fadeInOut {
  0% { opacity: 0.5; }
  50% { opacity: 1; }
  100% { opacity: 0.5; }
}
</style>
