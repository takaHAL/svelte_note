<script>
  import { push } from 'svelte-spa-router';
  import TopAppBar, {Row, Section, Title} from '@smui/top-app-bar';
  import IconButton from '@smui/icon-button';

  let prominent = false;
  let dense = false;
  let secondaryColor = false;
  export let appBarSettings = {
    leftIcon: 'menu',
    backLink: '',
    rightIcon: ''
  };
  export let eventMethod = function() {}
  const handleClick = function (link) {
    appBarSettings.backLink != '' ? appBarSettings.backLink : '/'
  }
</script>

<TopAppBar variant="static" {prominent} {dense} color={secondaryColor ? 'secondary' : 'primary'}>
  <Row>
    <Section>
        <IconButton class="material-icons" on:click={() => handleClick(appBarSettings.backLink)}>{appBarSettings.leftIcon}</IconButton>
        <Title on:click={() => push('/')}>初めてのSvelte</Title>
    </Section>
    {#if appBarSettings.rightIcon != ''}
    <Section align="end" toolbar>
      <IconButton on:click={eventMethod} class="material-icons" aria-label="delete">{appBarSettings.rightIcon}</IconButton>
    </Section>
    {/if}
  </Row>
</TopAppBar>