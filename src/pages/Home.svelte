<script>
  import NoteList from '../components/NoteList.svelte';
  import { loadNotes } from '../lib/storage';
  import AddButton from '../components/CircleButton.svelte';
  import TopAppBar from '../components/TopAppBar.svelte';
  const userNotes = loadNotes();
</script>

<div>
  <TopAppBar></TopAppBar>
  <div class="flexor-content">
    <NoteList notes={userNotes}></NoteList>
  </div>
  <div class="add-button">
    <AddButton iconName="add"></AddButton>
  </div>
</div>

<style>
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