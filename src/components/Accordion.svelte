<script>
  import { slide } from 'svelte/transition';
  import {
    GithubIcon
  } from 'svelte-feather-icons';

  export let items = [
    {
      id: 0,
      title: 'Accordion item 1',
      subtitle: 'Gist',
      description: 'description',
      open: false
    },
    {
      id: 1,
      title: 'Accordion item 2',
      subtitle: 'Gist',
      description: 'description',
      open: false
    },
    {
      id: 2,
      title: 'Accordion item 2',
      subtitle: 'Gist',
      description: 'description',
      open: false
    }
  ];

  const toggleAccordion = selectedItem => {
    items = items.map(item => {
      if (selectedItem.id === item.id) {
        item.open = !item.open;
      } else {
        item.open = false;
      }

      return item;
    });
  };
</script>

<style>
  .accordion {
    background-color: var(--gray-900);
    border-radius: 0.25rem;
    border: 1px solid var(--gray-600);
  }

  .accordion-item {
    padding: 0.75rem 1rem;
    background-color: var(--gray-700);
    color: var(--gray-200);
  }

  .accordion-item:not(:last-child) {
    border-bottom: 1px solid var(--gray-600)
  }

  .item-header {
    display: flex;
    flex-direction: column;
    position: relative;
    cursor: pointer;
  }

  .item-title {
    font-size: 1.2rem;
    width: 80%;
  }

  .item-subtitle {
    font-size: 0.85rem;
    width: 80%;
  }

  .item-expand {
    position: absolute;
    right: 2rem;
    display: flex;
    align-items: center;
    height: 100%;
    font-weight: bold;
  }

  .item-body {
    margin-top: 1rem;
    background-color: var(--gray-800);
    border-radius: 0.25rem;
    padding: 0.5rem;
    font-size: 0.9rem;
  }

  .item-body a {
    color: var(--gray-200);
    display: flex;
    align-items: center;
  }
</style>

<div class='accordion'>
  {#each items as item}
    <div class='accordion-item'>
      <div class='item-header' on:click={() => toggleAccordion(item)}>
        <div class='item-title'>{item.title}</div>
        <div class='item-subtitle'>{item.subtitle}</div>
        <div class='item-expand'>{item.open ? 'x' : '+'}</div>
      </div>
      {#if item.open}
        <div class='item-body' transition:slide>
          <div class='item-body-description'>
            {item.description}
          </div>
          <br />
          <div class='item-body-stack'>
            <b>Technologies used:</b> {item.stack.join(' | ')}
          </div>
          <br />
          <a href={item.url} target="_blank" rel="noopener noreferrer">
            <GithubIcon size='16' /> &nbsp;View Source
          </a>
        </div>
      {/if}
    </div>
  {/each}
</div>