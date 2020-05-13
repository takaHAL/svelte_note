<script>
  import Textfield, {Input, Textarea} from '@smui/textfield';
  export let title;
  export let content;
</script>
<div class="editor">
  <div class="editor-title">
    <Textfield bind:value={title} label="タイトル" input$aria-controls="helper-text-standard-a" input$aria-describedby="helper-text-standard-a" />
  </div>
  <div class="editor-content">
    <Textfield textarea bind:value={content} input$maxlength="140" input$aria-controls="helper-text-textarea" input$aria-describedby="helper-text-textarea" />
  </div>
</div>

<style>
  .editor {
    display: flex;
    flex-direction: column;
    height: 100%;
  }

  .editor-title {
    display: block;
    margin: 0 auto 20px;
  }

  .editor-content {
    flex: 1;
    display: block;
    margin: 0 auto;
  }
  :global(.mdc-text-field) {
    width: 90vw;
    font-size: 2em;
  }

  :global(.mdc-text-field--textarea .mdc-text-field__input) {
    resize: none;
    letter-spacing: 0.3em;
    width: 90vw !important;
    height: 50vh !important;
  }
</style>