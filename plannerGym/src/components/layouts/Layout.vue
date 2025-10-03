<script setup></script>

<template>
  <header>
    <h1 class="text-gradient">SMOLGRAM</h1>
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
