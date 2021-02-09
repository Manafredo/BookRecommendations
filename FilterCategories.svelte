<script>
  export let filter = "all";
  export let onclick = clicked => {};
  $: onclick(filter);
</script>

<div class="filterCategories btn-group stack-exception">
  <button class="btn toggle-btn" class:btn__primary={filter === 'Politiker'} aria-pressed={filter === 'all'} on:click={()=> filter = 'Politiker'} >
    <span>Politiker</span>
  </button>
  <button class="btn toggle-btn" class:btn__primary={filter === 'Influencer'} aria-pressed={filter === 'active'} on:click={()=> filter = 'Influencer'} >
    <span>Influencer</span>
  </button>
  <button class="btn toggle-btn" class:btn__primary={filter === 'Sonstiges'} aria-pressed={filter === 'completed'} on:click={()=> filter = 'Sonstiges'} >
    <span>Sonstiges</span>
  </button>
</div>