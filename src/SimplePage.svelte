<script>
  let value = '';
</script>

<main class="min-h-screen flex items-center justify-center p-4">
  <div class="w-full max-w-xs space-y-4 bg-gray-900/60 border border-gray-700 rounded-xl p-6">
    <h2 class="text-2xl font-bold text-center">Simple Demo</h2>
    <input
      type="text"
      placeholder="Type here..."
      bind:value={value}
      class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded text-white placeholder-gray-500 focus:outline-none focus:border-blue-500"
    />
    <p class="text-center text-gray-300">You typed: <span class="text-blue-400">{value}</span></p>
  </div>
</main>
