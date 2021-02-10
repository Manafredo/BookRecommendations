<script>
  import FilterCategories from "./FilterCategories.svelte";
  export let persons = [];

  let filter = "all";
  const filterPersons = (filter, persons) =>
    filter === "Politiker"
      ? persons.filter(p => p.fields.category == "Politiker")
      : filter === "Entrepreneur"
      ? persons.filter(p => p.fields.category == "Entrepreneur")
      : persons;
</script>

<style>
</style>

<main>
<FilterCategories bind:filter/>
  <ul>
	{#each filterPersons(filter,persons) as person}
		<h2>{person["fields"]["name"]}</h2>
		<p>{person["fields"]["description"]}</p>
	{/each}
  </ul>
</main>