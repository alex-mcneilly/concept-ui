<script lang="ts">
  import Sidebar from './Sidebar.svelte';
  import Navbar from './Navbar.svelte';
  import Dashboard from './Dashboard.svelte';
  import ConceptCardsDAG from './GraphPage.svelte';
  
  let currentPage = 'Dashboard';

  function handlePageChange(page: string) {
    currentPage = page;
  }
</script>

<main>
  <Sidebar on:pageChange={handlePageChange} />
  <div class="content">
    <Navbar {currentPage} />
    <div class="page-content">
      {#if currentPage === 'Dashboard'}
        <Dashboard />
      {:else if currentPage === 'Concept Cards'}
        <ConceptCardsDAG />
      {/if}
      <!-- Add other page components here -->
    </div>
  </div>
</main>

<style>
  main {
    display: flex;
    height: 100vh;
  }
  .content {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
  }
  .page-content {
    flex-grow: 1;
    padding: 20px;
    background-color: #f0f0f0;
  }
</style>