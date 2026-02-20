<script>
  let inputValue = '';
  let clicked = false;

  function handleClick() {
    clicked = true;
  }
</script>

<main class="min-h-screen flex items-center justify-center p-4">
  <div class="space-y-6 w-full max-w-md">
    <h1 class="text-4xl font-bold text-center">Lab</h1>
    
    <div class="space-y-4">
      <input
        type="text"
        placeholder="Enter something..."
        bind:value={inputValue}
        class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded text-white placeholder-gray-500 focus:outline-none focus:border-blue-500"
      />
      
      <button
        on:click={handleClick}
        class="w-full px-4 py-2 bg-blue-600 hover:bg-blue-700 rounded font-semibold transition"
      >
        Click me
      </button>
    </div>

    {#if clicked}
      <p class="text-center text-gray-300">You said: <span class="text-blue-400">{inputValue || '(nothing)'}</span></p>
    {/if}
  </div>
</main>
