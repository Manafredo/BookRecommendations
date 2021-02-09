<script>
  import FilterCategories from "./FilterCategories.svelte";
  import Persons from "./Persons.svelte";

  import { onMount } from "svelte";

  let persons = [];
  let filter;

  onMount(async function() {
    const response = await fetch(
      "https://cdn.contentful.com/spaces/t170cpyn3oju/environments/master/entries/?content_type=person&include=0&select=sys.id,fields&access_token=MFnR8m8akJLpWiIGbewXZi_PgdWJ0lWv46tjhf7g4uU"
    );
    persons = await response.json();
    persons = persons.items;
  });
</script>

<style>
</style>


<Persons {persons}/>