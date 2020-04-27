<div class="home">
  <h1 class="app-title">Svelte Note</h1>
  <NoteList notes={userNotes}></NoteList>
  <button class="add" on:click={() => push('/add')}>+新しいノート</button>
</div>

<script>
  import { push } from 'svelte-spa-router';
  import NoteList from './components/NoteList.svelte';

  const userNotes = [
    { title: 'テストノート', content: 'これはテストです！' },
    { title: 'やることリスト', content: '・Svleteの勉強\n・アプリ作成\n・公開' }
  ];
</script>

<style>
	.app-title {
		margin-bottom: 1em;
  }

  .home {
    width: 80%;
    margin: 0 auto;
  }

	.add {
		display: block;
		background-color: rgb(75, 168, 51);
		border: none;
		box-shadow: 0 0 6px rgba(0, 0, 0, 0.3);
		color: white;
		font-size: 1.5em;
		width: 100%;
		padding: 0.5em 0;
		margin: 1em 0;
		cursor: pointer;
	}
</style>