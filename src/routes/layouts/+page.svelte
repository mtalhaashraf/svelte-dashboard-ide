<script>
// @ts-nocheck

  import Pane from '../components/pane/pane.svelte';
  import Box from '../components/box/box.svelte';
  import Tab from '../components/tab/tab.svelte';

  let paneSize = '300px';
  let currentTab = 'Problems';
  const tabs = ['Problems', 'Output', 'Debug Console'];
</script>

<div class="ide-layout">
  <!-- Sidebar -->
  <Pane bind:size={paneSize} resizable={true} closable={true} maximizable={true} defaultSize="300px">
    <Box scrollable={true}>
      <h3>Explorer</h3>
      <ul>
        <li>File 1</li>
        <li>File 2</li>
        <li>File 3</li>
      </ul>
    </Box>
  </Pane>

  <!-- Main Content -->
  <div class="main-content">
    <Tab bind:activeTab={currentTab} tabs={tabs}>
      <div slot="Problems">
        <h3>Problems</h3>
        <p>No problems detected.</p>
      </div>
      <div slot="Output">
        <h3>Output</h3>
        <p>Build successful.</p>
      </div>
      <div slot="Debug Console">
        <h3>Debug Console</h3>
        <p>Debug logs appear here.</p>
      </div>
    </Tab>
  </div>
</div>

<style>
  .ide-layout {
    display: flex;
    height: 100vh;
  }

  .main-content {
    flex: 1;
    display: flex;
    flex-direction: column;
  }
</style>
