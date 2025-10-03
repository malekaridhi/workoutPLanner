<script setup>
import { ref, onMounted } from "vue";
const theme = ref("light");
onMounted(() => {
  const saved = localStorage.getItem("theme");
  if (saved) {
    theme.value = saved;
    document.documentElement.setAttribute("data-theme", saved);
  }
});
function toggleTheme() {
  theme.value = theme.value === "light" ? "dark" : "light";
  document.documentElement.setAttribute("data-theme", theme.value);
  localStorage.setItem("theme", theme.value);
}
</script>

<template>
  <header>
    <h1 class="text-gradient">GYMOGRAM</h1>
    <button @click="toggleTheme" class="theme-btn">
      <i v-if="theme === 'light'" class="fa-solid fa-moon"></i>
      <i v-else class="fa-solid fa-sun"></i>
    </button>
  </header>
  <main>
    <slot />
  </main>
  <footer>
    <small>Created by</small>
    <a href="https://www.github.com/malekaridhi" target="_blank">
      <img
        alt="pfp"
        src="https://media.licdn.com/dms/image/v2/D4D35AQGCeh_0RbG52w/profile-framedphoto-shrink_200_200/B4DZlxst_XJEAY-/0/1758549172509?e=1760094000&v=beta&t=dCYeY5gcMvzIpu-5wR8iGAtcD843XLhzYUTrZT9iKQ4"
      />
      <p>Malek</p>
      <i class="fa-brands fa-github"></i>
    </a>
  </footer>
</template>

<style scoped>
header,
footer,
main {
  padding: 1rem;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}
header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
main {
  flex: 1;
}

footer {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  align-items: center;
  padding: 2rem 0;
  padding-bottom: 3rem;
}

footer a {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.3rem;
  padding-right: 0.5rem;
  background: var(--background-muted);
  border-radius: 4rem;
  border: 1px solid transparent;
  transition-duration: 200ms;
  text-decoration: none;
}

footer a:hover {
  border-color: var(--color-link);
}

footer a img {
  max-width: 30px;
  aspect-ratio: 1 / 1;
  border-radius: 100%;
}
</style>
