<script>
  import AuthForm from './lib/components/AuthForm.svelte';
</script>

<style>
  :global(body) {
    background-color: #1F2732;
    color: white;
  }

  main {
    background-color: #1F2732;
    color: white;
  }
</style>

<main class="flex items-center justify-center min-h-screen">
  <!-- Left Side -->
  <div class="flex-1 flex items-center justify-center">
    <div class="flex items-center space-x-4">
      <!-- SVG Circle logo -->
      <img src="logo.svg" alt="VOLEJBOLS!!!!" class="" width="150" height="150">
      <!-- DPVK Logo -->
      <img src="DPVK.svg" alt="DPVK" class="" width="350" height="350">
    </div>
  </div>

  <!-- Right Side - Auth Component -->
  <div class="flex-1 flex justify-center">
    <AuthForm />
  </div>
</main>