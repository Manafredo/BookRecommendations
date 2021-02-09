<script>
 export let persons = [];
 export let filter = "all";

 const filterPersons = (filter, persons) =>
   filter === "Politiker"
     ? persons.filter(person => person.fields.category == "Politiker")
     : filter === "Entrepreneur"
     ? persons.filter(person => person.fields.category == "Entrepreneur")
     : persons;
</script>

<style>
</style>

<main>
<div class="filterCategories btn-group stack-exception">
  <button class="btn toggle-btn" class:btn__primary={filter === 'Politiker'} aria-pressed={filter === 'Politiker'} on:click={()=> filter = 'Politiker'} >
    <span>Politiker</span>
  </button>
  <button class="btn toggle-btn" class:btn__primary={filter === 'Entrepreneur'} aria-pressed={filter === 'Entrepreneur'} on:click={()=> filter = 'Entrepreneur'} >
    <span>Entrepreneur</span>
  </button>
  <button class="btn toggle-btn" class:btn__primary={filter === 'Sonstiges'} aria-pressed={filter === 'completed'} on:click={()=> filter = 'Sonstiges'} >
    <span>Alle</span>
  </button>
</div>
  <ul>
	{#each filterPersons(filter,persons) as person}
		<h2>{person["fields"]["name"]}</h2>
		<p>{person["fields"]["description"]}</p>
	{/each}
  </ul>
</main>