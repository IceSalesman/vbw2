<script>
    export let activeTab = 'login';
  
    const toggleTab = (tab) => {
      activeTab = tab;
    };
  </script>
  
  <style>
    .slider {
      position: absolute;
      background-color: #f56565; /* bg-red-500 */
      height: 100%;
      width: 50%;
      border-radius: 9999px; /* rounded-full */
      transition: transform 0.3s ease-in-out; /* transition-transform duration-300 ease-in-out */
    }
  
    .dark-bg {
      background-color: #2D3748; /* Slightly lighter dark background */
    }
  
    .dark-text {
      color: white;
    }
  
    .dark-border {
      border-color: #2D3748;
    }
  
    .dark-input {
      width: 100%;
      padding: 0.5rem;
      border: 1px solid;
      border-radius: 0.25rem;
      outline: none;
      transition: box-shadow 0.2s;
      &:focus {
        box-shadow: 0 0 0 2px rgba(248, 113, 113, 0.5);
      }
    }
  
    .dark-button {
      width: 100%;
      background-color: #f56565; /* bg-red-500 */
      color: white;
      padding-top: 0.5rem; /* py-2 */
      padding-bottom: 0.5rem; /* py-2 */
      border-radius: 0.25rem; /* rounded */
      transition: background-color 0.2s; /* transition */
      &:hover {
        background-color: #e53e3e; /* hover:bg-red-600 */
      }
    }
  </style>
  
  <div class="dark-bg rounded-lg shadow-lg p-6 w-96">
    <!-- Toggle Buttons -->
    <div class="relative flex bg-gray-700 rounded-full mb-6">
      <button
        class="w-1/2 py-2 dark-text font-semibold z-10"
        on:click={() => toggleTab('login')}
        class:text-white={activeTab === 'login'}
      >
        Login
      </button>
      <button
        class="w-1/2 py-2 dark-text font-semibold z-10"
        on:click={() => toggleTab('register')}
        class:text-white={activeTab === 'register'}
      >
        Register
      </button>
      <!-- Slider -->
      <div
        class="slider"
        style="transform: translateX({activeTab === 'register' ? '100%' : '0'});"
      ></div>
    </div>
  
    <!-- Forms -->
    {#if activeTab === 'login'}
      <form class="space-y-4">
        <input
          type="text"
          placeholder="Username"
          class="dark-input dark-border"
        />
        <input
          type="password"
          placeholder="Password"
          class="dark-input dark-border"
        />
        <button
          type="submit"
          class="dark-button"
        >
          Login
        </button>
      </form>
    {:else}
      <form class="space-y-4">
        <input
          type="text"
          placeholder="Username"
          class="dark-input dark-border"
        />
        <input
          type="email"
          placeholder="Email"
          class="dark-input dark-border"
        />
        <input
          type="password"
          placeholder="Password"
          class="dark-input dark-border"
        />
        <button
          type="submit"
          class="dark-button"
        >
          Register
        </button>
      </form>
    {/if}
  </div>