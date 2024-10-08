<script lang="ts">
  export let currentPage: string;

  const profileImageUrl = "/api/placeholder/40/40"; // Placeholder for profile image
</script>

<nav>
  <div class="logo">Kodless</div>
  <h1>{currentPage}</h1>
  <div class="profile">
    <img src={profileImageUrl} alt="Profile" />
  </div>
</nav>

<style>
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    background-color: #ffffff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  .logo {
    font-weight: bold;
    font-size: 1.5rem;
  }

  h1 {
    font-size: 1.2rem;
    margin: 0;
  }

  .profile img {
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
</style>