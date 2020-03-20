<script>
  import { 
    MenuIcon
  } from 'svelte-feather-icons';
  import { showAside } from '../store/stores.js';

  const menuClick = event => {
    event.stopPropagation();
    showAside.update(val => !val);
  }
</script>

<style>
  .app-header {
    min-height: var(--header-height);
    background-color: var(--dark-foreground);
    margin: 0.5rem;
    border-radius: 0.5rem;
    display: flex;
    position: relative;
    justify-content: center;
    align-items: center;
    color: var(--gray-200);
  }

  .app-header span {
    font-size: 2rem;
    font-weight: bold;
  }

  .hamburger {
    position: absolute;
    left: 1.5rem;
  }
</style>

<div class='app-header'>
  <span>Priyanjit Dey</span>
  <div class='hamburger' on:click={menuClick}>
    <span><MenuIcon size='24' /></span>
  </div>
</div>