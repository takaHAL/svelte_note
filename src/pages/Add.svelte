<script>
  import { push } from 'svelte-spa-router';
  import NoteEditor from '../components/NoteEditor.svelte';
  import { addNote } from '../lib/storage';
  import TopAppBar from '../components/TopAppBar.svelte';
  import SaveButton from '../components/CircleButton.svelte';

  let title = '新規メモ';
  let content = '';
  const appBarSettings = {
    leftIcon: 'arrow_back_ios',
    backLink: '/',
    rightIcon: ''
  }

  const onSave = () =>  {
    addNote({title, content});
    push('/');
  };
</script>
<div>
  <TopAppBar appBarSettings={appBarSettings}></TopAppBar>
  <div class="add flexor-content">
    <NoteEditor bind:title={title} bind:content={content}></NoteEditor>
    <div class="add-button">
      <SaveButton iconName="save_alt" eventMethod={onSave} disabled={!title || !content}></SaveButton>
    </div>
  </div>
</div>

<style>
  .add {
    display: flex;
    flex-direction: column;
    height: 0%;
  }
  .add-button {
    position: fixed;
    right: 25px;
    bottom: 50px;
  }
  .flexor-content {
    flex-basis: 0;
    flex-grow: 1;
    height: 80vh;
    overflow: auto;
    -ms-overflow-style: none;    /* IE, Edge 対応 */
    scrollbar-width: none;       /* Firefox 対応 */
  }
  .flexor-content::-webkit-scrollbar {  /* Chrome, Safari 対応 */
    display:none;
  }

</style>