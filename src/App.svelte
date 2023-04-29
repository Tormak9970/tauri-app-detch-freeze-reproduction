<script lang="ts">
  import ImageFetcher from './lib/ImageFetcher.svelte';
</script>

<main class="container">
  <h1 style="margin-bottom: 0px;">Minimal Reproduction of App Freezing</h1>
  <h1>Caused by Fetching APNGs</h1>

  <div class="row">
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo vite" alt="Vite Logo" />
    </a>
    <a href="https://tauri.app" target="_blank">
      <img src="/tauri.svg" class="logo tauri" alt="Tauri Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank">
      <img src="/svelte.svg" class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>

  <p>
    Click on the button below to test the APNG fetch.
  </p>

  <div class="row">
    <ImageFetcher />
  </div>


</main>

<style>
  .logo.vite:hover {
    filter: drop-shadow(0 0 2em #747bff);
  }

  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00);
  }
</style>