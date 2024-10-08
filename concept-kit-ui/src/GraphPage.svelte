<script lang="ts">
  import ConceptCard from './ConceptCard.svelte';

  // Sample data, replace with actual data in your application
  const concepts = [
    {
      name: 'Comment',
      description: 'Handles user comments on design elements.',
      actions: ['Create', 'Update', 'Delete'],
      version: '1.0.0',
      lastUpdated: '2023-04-15'
    },
    // Add more concept objects here
  ];
</script>

<div class="concept-cards-dag">
  <h2>Concept Cards</h2>
  <div class="cards-container">
    {#each concepts as concept}
      <ConceptCard {...concept} />
    {/each}
  </div>
</div>

<style>
  .concept-cards-dag {
    padding: 2rem;
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
  }

  .cards-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
  }
</style>