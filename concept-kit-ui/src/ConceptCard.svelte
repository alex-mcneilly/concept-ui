<script lang="ts">
  export let name: string;
  export let description: string;
  export let actions: string[];
  export let version: string;
  export let lastUpdated: string;

  function handleDragStart(event: DragEvent) {
    if (event.dataTransfer) {
      event.dataTransfer.setData('text/plain', name);
    }
  }

  function handleEditConcept() {
    // Implement edit concept functionality
  }

  function handleViewDependencies() {
    // Implement view dependencies functionality
  }

  function handleViewSyncs() {
    // Implement view syncs functionality
  }
</script>

<div class="concept-card" draggable="true" on:dragstart={handleDragStart}>
  <div class="header">
    <h3>{name}</h3>
    <div class="buttons">
      <button class="see-code">&#60;/&#62;</button>
      <div class="dropdown">
        <button class="dropbtn">⋯</button>
        <div class="dropdown-content">
          <a href="#" on:click={handleEditConcept}>Edit Concept</a>
          <a href="#" on:click={handleViewDependencies}>View Dependencies</a>
        </div>
      </div>
    </div>
  </div>
  <p>{description}</p>
  <div class="actions">
    <h4>Actions:</h4>
    <ul>
      {#each actions as action}
        <li>{action}</li>
      {/each}
    </ul>
  </div>
  <button class="view-syncs" on:click={handleViewSyncs}>View Syncs</button>
  <div class="footer">
    <span class="version">v{version}</span>
    <span class="last-updated">Updated: {lastUpdated}</span>
  </div>
</div>

<style>
  .concept-card {
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 1rem;
    margin: 1rem;
    background-color: white;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

  h3 {
    margin: 0;
    font-weight: bold;
  }

  .buttons button {
    width: 30px;
    height: 30px;
    border: 1px solid #ccc;
    border-radius: 4px;
    background-color: white;
    cursor: pointer;
    margin-left: 0.5rem;
  }

  .dropdown {
    position: relative;
    display: inline-block;
  }

  .dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;
    right: 0;
  }

  .dropdown:hover .dropdown-content {
    display: block;
  }

  .dropdown-content a {
    color: black;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
  }

  .dropdown-content a:hover {
    background-color: #f1f1f1;
  }

  .actions {
    margin-top: 1rem;
  }

  .view-syncs {
    width: 100%;
    padding: 0.5rem;
    margin-top: 1rem;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }

  .footer {
    display: flex;
    justify-content: space-between;
    margin-top: 1rem;
    font-size: 0.8rem;
    color: #666;
  }
</style>