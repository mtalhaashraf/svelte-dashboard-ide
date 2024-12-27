<script>
    import { writable } from 'svelte/store';
  
    export let size = '300px'; // Default size
    export let resizable = true;
    export let closable = true;
    export let maximizable = true;
    export let defaultSize = '300px';
  
    const paneSize = writable(size);
  
    function resetSize() {
      paneSize.set(defaultSize);
    }
  
    function maximize() {
      paneSize.set('100%');
    }
  </script>
  
  <div
    class="pane"
    style="width: {$paneSize}; resize: {resizable ? 'horizontal' : 'none'};"
  >
    <slot />
  
    {#if closable}
      <button on:click={() => paneSize.set('0px')}>Close</button>
    {/if}
  
    {#if maximizable}
      <button on:click={maximize}>Maximize</button>
    {/if}
  
    <button on:click={resetSize}>Reset</button>
  </div>
  
  <style>
    .pane {
      border: 1px solid #ccc;
      padding: 10px;
      overflow: auto;
    }
  </style>
  