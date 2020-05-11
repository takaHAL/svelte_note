<script>
  import { push } from 'svelte-spa-router';
  import Fab, {Label, Icon} from '@smui/fab';
  import FormField from '@smui/form-field';

  export let route = '/add';
  export let iconName;
  export let disabled = false;
  export let eventMethod = function() {
    push(route)
  }
</script>

<Fab color="primary" on:click={eventMethod} disabled={disabled}>
  <Icon class="material-icons">{iconName}</Icon>
</Fab>