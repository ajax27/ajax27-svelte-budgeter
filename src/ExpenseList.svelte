<script>
  import SectionTitle from './Title.svelte';
  import Expense from './Expense.svelte';
  import { fly } from 'svelte/transition';
  import { flip } from 'svelte/animate';
  export let expenses = [];
</script>

<style>
  h2 {
    text-transform: capitalize;
  }
</style>

<section>
  <SectionTitle title="my expense list" />
  <ul>
    {#each expenses as expense, index (expense.id)}
    <div in:fly={{ x: 400, delay: index * 600 }} out:fly={{ x: - 400}} animate:flip>
      <Expense {...expense} />
    </div>
      {:else}
      <h2>currently no expenses to show</h2>
    {/each}
  </ul>
</section>





