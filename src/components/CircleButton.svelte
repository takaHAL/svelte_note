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

<Fab color="primary" class="material_circle_button" on:click={eventMethod} disabled={disabled}>
  <Icon class="material-icons">{iconName}</Icon>
</Fab>

<style>
  :global(.material_circle_button[disabled]) {
    pointer-events: none;
    opacity: 0.6;
  }
</style>