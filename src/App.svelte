<script>
  import AuthForm from './lib/components/AuthForm.svelte';
  import { fly, fade } from 'svelte/transition';
</script>

<style>
  :global(body) {
    background-color: #24323c;
    color: white;
  }

  main {
    background-color: #24323c;
    color: white;
  }
</style>

<main class="flex items-center justify-center min-h-screen">
  <!-- Left Side -->
  <div class="flex-1 flex items-center justify-center">
    <div class="flex items-center space-x-4">
      <!-- SVG Circle logo -->
      <img src="logo.svg" alt="VOLEJBOLS!!!!" class="" width="150" height="150" transition:fly="{{ x: -300, duration: 1000 }}">
      <!-- DPVK Logo -->
      <img src="DPVK.svg" alt="DPVK" class="" width="400" height="400" transition:fly="{{ x: 300, duration: 1000 }}">
    </div>
  </div>

  <!-- Right Side - Auth Component -->
  <div class="flex-1 flex justify-center" transition:fade="{{ duration: 1000 }}">
    <AuthForm />
  </div>
</main>