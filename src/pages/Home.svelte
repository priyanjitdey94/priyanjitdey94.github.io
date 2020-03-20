<script>
  import Header from '../components/Header.svelte';
  import About from '../components/About.svelte';
  import Content from '../components/Content.svelte';
  import { showAside } from '../store/stores.js';

  const resizeHandler = event => {
    let width = event.target.innerWidth;

    if (width > 992 && $showAside) {
      showAside.set(false);
    }
  };

  const hideAside = () => {
    if ($showAside) {
      showAside.set(false);
    }
  };
</script>

<style>
  :global(body) {
    --aside-width:   320px;
    --header-height: 60px;

    --white:    #fff;
    --gray-100: #f8f9fa;
    --gray-200: #e9ecef;
    --gray-300: #dee2e6;
    --gray-400: #ced4da;
    --gray-500: #adb5bd;
    --gray-600: #6c757d;
    --gray-700: #495057;
    --gray-800: #343a40;
    --gray-900: #212529;
    --black:    #000;

    --blue:    #007bff;
    --indigo:  #6610f2;
    --purple:  #6f42c1;
    --pink:    #e83e8c;
    --red:     #dc3545;
    --orange:  #fd7e14;
    --yellow:  #ffc107;
    --green:   #28a745;
    --teal:    #20c997;
    --cyan:    #17a2b8;

    --primary:       var(--blue);
    --secondary:     var(--gray-600);
    --success:       var(--green);
    --info:          var(--cyan);
    --warning:       var(--yellow);
    --danger:        var(--red);
    --light:         var(--gray-100);
    --dark:          var(--gray-800);

    --dark-foreground: #2e363d;
    --dark-background: #24292E;

    padding: 0;
    margin: 0;
		font-family: 'IBM Plex Sans', sans-seriff;
    background-color: var(--dark-background);
  }

	.app-wrapper {
    min-height: 100vh;
    position: relative;
	}

  .app-header-wrapper {
    display: none;
    top: 0;
  }

  .app-aside-wrapper {
    position: fixed;
    width: var(--aside-width);
    min-height: 100vh;
    transform: translateX(calc(-1 * var(--aside-width)));
    transition: transform 0.3s ease;
    top: 0.5rem;
    z-index: 1000;
  }

  .show-aside {
    transform: translateX(0px);
  }
  
  .blur-bg {
    -webkit-filter: blur(3px);
    -moz-filter: blur(3px);
    -o-filter: blur(3px);
    -ms-filter: blur(3px);
    filter: blur(3px);
  }

  .cover-bg {
    opacity: 0;
    height: 100vh;
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
  }

  .app-content-wrapper {
    margin-left: var(--aside-width);
  }

  @media screen and (min-width: 992px) {
    .app-aside-wrapper {
      transform: translateX(0px);
    }
  }

  @media screen and (max-width: 992px) {
    .app-content-wrapper {
      margin-left: 0px;
    }

    .app-header-wrapper {
      display: block;
    }
  }
</style>

<svelte:window on:resize={resizeHandler} />

<div class='app-wrapper'>
  <div class={'app-header-wrapper' + ($showAside ? ' blur-bg' : '')}>
    <Header />
  </div>
  <div class={'app-content-wrapper' + ($showAside ? ' blur-bg' : '')}>
    <Content />
  </div>
  <div class={'app-aside-wrapper' + ($showAside ? ' show-aside' : '')}>
    {#if $showAside}
      <div class='cover-bg' on:click={hideAside}></div>
    {/if}
    <About />
  </div>
</div>
