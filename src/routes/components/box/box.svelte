
<!-- Box.svelte -->
<script>
    export let scrollable = false;
  </script>
  
  <div class="box" style="overflow: {scrollable ? 'auto' : 'visible'}">
    <slot />
  </div>
  
  <style>
    .box {
      border: 1px solid #ccc;
      padding: 10px;
      margin: 5px;
    }
  </style>
  
  <!-- Box END -->