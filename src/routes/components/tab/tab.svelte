<script>
    import { writable } from 'svelte/store';
  
    /**
	 * @type {any[]}
	 */
    export let tabs = [];
    export let activeTab = tabs[0] || ''; // Default to first tab
    const active = writable(activeTab);

    // Sync the activeTab prop with the writable store
    $: activeTab = $active;
</script>
  
<div class="tabs">
  <div class="tab-header">
    {#each tabs as tab}
      <button
        class="tab-button {tab === $active ? 'active' : ''}"
        on:click={() => active.set(tab)}
      >
        {tab}
      </button>
    {/each}
  </div>

  <div class="tab-content">
    {#each tabs as tab}
      {#if activeTab === tab}
        <slot />
      {/if}
    {/each}
  </div>
</div>

<style>
  .tabs {
    border: 1px solid #ccc;
  }

  .tab-header {
    display: flex;
  }

  .tab-button {
    padding: 10px;
    cursor: pointer;
  }

  .tab-button.active {
    background-color: #007acc;
    color: white;
  }

  .tab-content {
    padding: 10px;
  }
</style>
