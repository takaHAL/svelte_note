<script>
  import { push } from 'svelte-spa-router';
  import NoteEditor from '../components/NoteEditor.svelte';
  import { addNote } from '../lib/storage';
  import TopAppBar from '../components/TopAppBar.svelte';

  let title = '新しいノート';
  let content = '';

  const onSave = () =>  {
    addNote({title, content});
    push('/');
  };
</script>
<div>
  <TopAppBar menuIcon='arrow_back_ios' backLink='/'></TopAppBar>
  <div class="add flexor-content">
    <NoteEditor bind:title={title} bind:content={content}></NoteEditor>
    <div class="button-container">
      <button class="save" on:click={onSave} disabled={!title || !content}>保存</button>
    </div>
  </div>
</div>

<style>
  .add {
    display: flex;
    flex-direction: column;
    height: 0%;
  }

  .button-container {
    padding: 1em 0;
    text-align: right;
  }

  .save {
    background-color: rgb(62, 68, 163);
    border: none;
    border-radius: 3px;
    color: white;
    font-size: 1em;
    padding: 0.5em 1em;
    cursor: pointer;
  }

  .save:disabled {
    opacity: 0.3;
    cursor: auto;
  }
  .flexor-content {
    flex-basis: 0;
    flex-grow: 1;
    height: 80%;
    overflow: auto;
  }
</style>