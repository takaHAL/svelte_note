<script>
  import { push } from 'svelte-spa-router';
  import NoteEditor from '../components/NoteEditor.svelte';
  import TopAppBar from '../components/TopAppBar.svelte';
  import { loadNotes, overwriteNote, deleteNote } from '../lib/storage';
  import SaveButton from '../components/CircleButton.svelte';
  export let params = {};

  const note = loadNotes()[params.id];

  let title = note.title;
  let content = note.content;
  const appBarSettings = {
    leftIcon: 'arrow_back_ios',
    backLink: '/',
    rightIcon: 'delete'
  }

  const onSave = () =>  {
    overwriteNote(params.id, {title, content});
    push('/');
  };
  const onDelete = () => {
    if(confirm("削除しますか？")) {
        deleteNote(params.id)
        push('/')
    }
  }
</script>
<div>
  <TopAppBar eventMethod={onDelete} appBarSettings={appBarSettings}></TopAppBar>
  <div class="add flexor-content">
    <NoteEditor bind:title={title} bind:content={content}></NoteEditor>
    <div class="add-button">
      <SaveButton iconName="save_alt" eventMethod={onSave}  disabled={!title || !content}></SaveButton>
    </div>
  </div>
</div>

<style>
  .add {
    display: flex;
    flex-direction: column;
    height: 100%;
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
