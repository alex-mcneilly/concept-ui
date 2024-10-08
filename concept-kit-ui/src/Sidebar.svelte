<script lang="ts">
  const menuItems = [
    { name: 'Dashboard', icon: '📊' },
    { name: 'Concept Cards', icon: '🗂️' },
    { name: 'Synchronizations', icon: '🔄' },
    { name: 'API Endpoints', icon: '🔗' },
    { name: 'Settings', icon: '⚙️' },
    { name: 'Help & Documentation', icon: '❓' },
  ];
</script>

<aside>
  <div class="logo">Kodless</div>
  <nav>
    {#each menuItems as item}
      <a href="#{item.name.toLowerCase().replace(' ', '-')}">
        <span class="icon">{item.icon}</span>
        {item.name}
      </a>
    {/each}
  </nav>
</aside>

<style>
  aside {
    width: 250px;
    background-color: #f0f0f0;
    padding: 20px;
  }
  .logo {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 20px;
  }
  nav a {
    display: block;
    padding: 10px 0;
    text-decoration: none;
    color: #333;
  }
  .icon {
    margin-right: 10px;
  }
</style>