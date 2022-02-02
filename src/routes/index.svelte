<script lang="ts">
  import { toJpeg } from 'html-to-image';

  function handleClick() {
    toJpeg(document.getElementById('container'))
      .then((dataUrl) => {
        const link = document.createElement('a');
        link.download = 'test-download.jpeg';
        link.href = dataUrl;
        link.click();
      })
      .catch((err) => console.log(err));
  }
</script>

<div id="container">
  <h1>Welcome to SvelteKit</h1>
  안녕하세요!
  <p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
</div>
<button type="button" on:click={handleClick}>다운로드</button>

<style lang="scss">
  #container {
    background: $base-color;
    border: 3px solid red;
    width: 500px;
  }
  h1 {
    color: blue;
  }
</style>
