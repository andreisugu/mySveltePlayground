<script>
  import { onMount } from 'svelte';
  import { Network } from 'vis-network/standalone';
  let container;

  onMount(() => {
    const nodes = [
      { id: 1, label: 'Node 1' },
      { id: 2, label: 'Node 2' },
      { id: 3, label: 'Node 3' }
    ];
    const edges = [
      { from: 1, to: 2 },
      { from: 1, to: 3 }
    ];
    const data = { nodes, edges };
    const options = { nodes: { color: '#60a5fa' }, edges: { color: '#fff' }, physics: false };
    new Network(container, data, options);
  });
</script>

<main class="min-h-screen flex items-center justify-center p-4">
  <div class="w-full max-w-md bg-gray-900/60 border border-gray-700 rounded-xl p-6">
    <h2 class="text-2xl font-bold text-center mb-4">vis-network Demo</h2>
    <div bind:this={container} style="height:300px; background:#222; border-radius:8px;"></div>
    <p class="text-center text-gray-400 mt-4 text-sm">A minimal interactive network using vis.js</p>
  </div>
</main>
