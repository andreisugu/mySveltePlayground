<script>
  import SimplePage from './SimplePage.svelte';
  let showSimple = false;
  let name = '';
  let goal = '';
  let submitted = false;
  let error = '';
  const maxChars = 120;

  $: remaining = maxChars - goal.length;
  $: tooLong = remaining < 0;

  function handleSubmit(event) {
    event.preventDefault();

    if (!name.trim() || !goal.trim()) {
      error = 'Please fill in both fields.';
      submitted = false;
      return;
    }

    if (tooLong) {
      error = `Goal is too long by ${Math.abs(remaining)} character(s).`;
      submitted = false;
      return;
    }

    error = '';
    submitted = true;
  }

  function resetForm() {
    name = '';
    goal = '';
    error = '';
    submitted = false;
  }
</script>

<div class="flex justify-center mt-4">
  <button
    class="px-4 py-2 bg-gray-800 text-white rounded hover:bg-gray-700 font-semibold transition mr-2"
    on:click={() => showSimple = false}
    disabled={!showSimple}
  >Main Form</button>
  <button
    class="px-4 py-2 bg-gray-800 text-white rounded hover:bg-gray-700 font-semibold transition"
    on:click={() => showSimple = true}
    disabled={showSimple}
  >Simple Demo</button>
</div>

{#if showSimple}
  <SimplePage />
{:else}
  <main class="min-h-screen flex items-center justify-center p-4">
    <div class="space-y-6 w-full max-w-md bg-gray-900/60 border border-gray-700 rounded-xl p-6">
    <h1 class="text-3xl font-bold text-center">Study Goal Form</h1>

    <form class="space-y-4" on:submit={handleSubmit}>
      <input
        type="text"
        placeholder="Your name"
        bind:value={name}
        class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded text-white placeholder-gray-500 focus:outline-none focus:border-blue-500"
      />

      <textarea
        rows="4"
        placeholder="What is one study goal for this week?"
        bind:value={goal}
        class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded text-white placeholder-gray-500 focus:outline-none focus:border-blue-500"
      ></textarea>

      <p class={`text-sm ${tooLong ? 'text-red-400' : 'text-gray-400'}`}>
        {tooLong ? `${Math.abs(remaining)} over the limit` : `${remaining} characters left`}
      </p>

      <button
        type="submit"
        class="w-full px-4 py-2 bg-blue-600 hover:bg-blue-700 rounded font-semibold transition"
      >
        Save Goal
      </button>
    </form>

    <button
      on:click={resetForm}
      class="w-full px-4 py-2 bg-gray-700 hover:bg-gray-600 rounded font-semibold transition"
    >
      Reset
    </button>

    {#if error}
      <p class="text-center text-red-400">{error}</p>
    {/if}

    {#if submitted}
      <div class="text-left text-gray-300 bg-gray-800/80 border border-gray-700 rounded p-4 space-y-2">
        <p><span class="text-blue-400 font-semibold">Name:</span> {name}</p>
        <p><span class="text-blue-400 font-semibold">Goal:</span> {goal}</p>
      </div>
    {/if}
    </div>
  </main>
{/if}
