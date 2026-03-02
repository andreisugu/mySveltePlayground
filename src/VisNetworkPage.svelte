<script>
  import { onMount } from 'svelte';
  import { Network } from 'vis-network/standalone';
  let container;

  onMount(() => {
    const nodes = [
      { id: 1, label: 'Svelte', color: '#ff3e00', shape: 'dot', size: 30, font: { color: '#fff', size: 20 } },
      { id: 2, label: 'Vite', color: '#646cff', shape: 'dot', size: 25, font: { color: '#fff', size: 18 } },
      { id: 3, label: 'Tailwind', color: '#38bdf8', shape: 'dot', size: 25, font: { color: '#fff', size: 18 } },
      { id: 4, label: 'vis.js', color: '#fbbf24', shape: 'star', size: 28, font: { color: '#222', size: 18 } },
      { id: 5, label: 'You', color: '#22d3ee', shape: 'diamond', size: 22, font: { color: '#fff', size: 16 } },
      { id: 6, label: 'JS', color: '#facc15', shape: 'triangle', size: 20, font: { color: '#222', size: 16 } }
    ];
    const edges = [
      { from: 1, to: 2, color: { color: '#818cf8' }, width: 2 },
      { from: 1, to: 3, color: { color: '#38bdf8' }, width: 2 },
      { from: 1, to: 4, color: { color: '#fbbf24' }, width: 2, dashes: true },
      { from: 2, to: 6, color: { color: '#facc15' }, width: 1 },
      { from: 3, to: 6, color: { color: '#facc15' }, width: 1 },
      { from: 4, to: 6, color: { color: '#facc15' }, width: 1, dashes: true },
      { from: 5, to: 1, color: { color: '#22d3ee' }, width: 2, arrows: 'to' },
      { from: 5, to: 2, color: { color: '#22d3ee' }, width: 2, arrows: 'to' },
      { from: 5, to: 3, color: { color: '#22d3ee' }, width: 2, arrows: 'to' }
    ];
    const data = { nodes, edges };
    const options = {
      nodes: {
        borderWidth: 2,
        shadow: true
      },
      edges: {
        smooth: {
          enabled: true,
          type: 'dynamic',
          roundness: 0.5
        },
        shadow: true
      },
      physics: {
        enabled: true,
        barnesHut: {
          gravitationalConstant: -2000,
          springLength: 120,
          springConstant: 0.04
        },
        stabilization: false
      },
      interaction: {
        hover: true,
        tooltipDelay: 100
      },
      layout: {
        improvedLayout: true
      }
    };
    new Network(container, data, options);
  });
</script>

<main class="min-h-screen flex items-center justify-center p-4">
  <div class="w-full max-w-md bg-gray-900/60 border border-gray-700 rounded-xl p-6">
    <h2 class="text-2xl font-bold text-center mb-4">vis-network Demo</h2>
    <div bind:this={container} style="height:340px; background:#222; border-radius:8px;"></div>
    <p class="text-center text-gray-400 mt-4 text-sm">A colorful, moving network using vis.js and all lab tech!</p>
  </div>
</main>
