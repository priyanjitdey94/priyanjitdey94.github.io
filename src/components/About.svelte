<script>
  import Separator from './Separator.svelte';
  import { 
    MapPinIcon,
    PhoneCallIcon,
    MailIcon,
    DownloadIcon,
    GithubIcon,
    FacebookIcon,
    TwitterIcon,
    LinkedinIcon,
    CodesandboxIcon,
    CodepenIcon
  } from 'svelte-feather-icons';
</script>

<style>
  .app-aside {
    position: relative;
    background-color: var(--dark-foreground);
    padding: 0.75rem 1.25rem 0 1.25rem;
    margin: 0rem 0.5rem;
    border-radius: 0.5rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: calc(100vh - 1.75rem);
    overflow-y: scroll;
  }

  @media screen and (max-width: 992px) {
    .app-aside {
      border: 1px solid var(--gray-600);
    }
  }

  .aside-container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .aside-avatar {
    min-width: 100px;
    min-height: 100px;
    border-radius: 50%;
    margin-top: 1rem;
    margin-bottom: 1rem;
    background-color: var(--gray-500);
  }

  .aside-title {
    color: var(--gray-200);
    font-size: 2rem;
    font-weight: bolder;
    margin: 0.5rem 0rem;
  }

  .aside-subtitle {
    color: var(--gray-400);
    margin-bottom: 0.5rem;
  }

  .aside-list-item {
    padding: 0.5rem;
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    color: var(--gray-300);
  }

  .aside-list-item-description {
    display: inline-block;
    font-size: 0.9rem;
    padding-left: 0.75rem;
  }

  .aside-footer {
    min-height: 60px;
    /* background-color: red; */
    margin-top: 1rem;
    border-top: 1px solid var(--gray-600);
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    width: 100%;
  }

  .aside-footer-icon {
    padding: 0 0.5rem;
    color: var(--gray-300);
  }
</style>

<div class='app-aside'>
  <div class='aside-container'>
    <div class='aside-avatar'></div>
    <div class='aside-title'>Priyanjit Dey</div>
    <div class='aside-subtitle'>JavaScript Developer</div>
    <Separator />
    <div class='aside-list-item'>
      <MapPinIcon size='18' />
      <span class='aside-list-item-description'>Kolkata, India</span>
    </div>
    <div class='aside-list-item'>
      <PhoneCallIcon size='18' />
      <span class='aside-list-item-description'>(+91) 9474851429</span>
    </div>
    <div class='aside-list-item'>
      <MailIcon size='18' />
      <span class='aside-list-item-description'>priyanjit.dey@gmail.com</span>
    </div>
    <Separator />
    <div class='aside-list-item'>
      <DownloadIcon size='18' />
      <span class='aside-list-item-description'>Download Résumé</span>
    </div>
  </div>
  <div class='aside-footer'>
    <a href='https://github.com/priyanjitdey94' class='aside-footer-icon' target="_blank" rel="noopener noreferrer">
      <GithubIcon size='24' />
    </a>
    <a href='https://www.facebook.com/priyanjit.dey.3/' class='aside-footer-icon' target="_blank" rel="noopener noreferrer">
      <FacebookIcon size='24' />
    </a>
    <a href='https://twitter.com/priyanjitdey94' class='aside-footer-icon' target="_blank" rel="noopener noreferrer">
      <TwitterIcon size='24' />
    </a>
    <a href='https://www.linkedin.com/in/priyanjit-dey-5b0101102/' class='aside-footer-icon' target="_blank" rel="noopener noreferrer">
      <LinkedinIcon size='24' />
    </a>
    <a href='https://codesandbox.io/u/priyanjitdey94' class='aside-footer-icon' target="_blank" rel="noopener noreferrer">
      <CodesandboxIcon size='24' />
    </a>
    <a href='https://codepen.io/priyanjitdey94' class='aside-footer-icon' target="_blank" rel="noopener noreferrer">
      <CodepenIcon size='24' />
    </a>
  </div>
</div>