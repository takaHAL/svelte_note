<script>
  import { push } from 'svelte-spa-router';
  import TopAppBar, {Row, Section, Title} from '@smui/top-app-bar';
  import IconButton from '@smui/icon-button';

  let prominent = false;
  let dense = false;
  let secondaryColor = false;
  export let menuIcon = 'menu';
  export let backLink = '';

  const handleClick = function (link) {
    backLink != '' ? backLink : '/'
  }
</script>

<TopAppBar variant="static" {prominent} {dense} color={secondaryColor ? 'secondary' : 'primary'}>
  <Row>
    <Section>
        <IconButton class="material-icons" on:click={() => push(backLink)}>{menuIcon}</IconButton>
        <Title on:click={() => push('/')}>練習ページ</Title>
    </Section>
  </Row>
</TopAppBar>