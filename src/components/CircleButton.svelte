<script>
  import { push } from 'svelte-spa-router';
  import Fab, {Label, Icon} from '@smui/fab';
  import FormField from '@smui/form-field';

  export let route = '/add';
</script>

<Fab color="primary" on:click={() => push(route)}>
  <Icon class="material-icons">add</Icon>
</Fab>