<script>
  import "../app.css";
</script>

<main class="h-screen">
    <div class="h-screen flex justify-center flex-col px-20 text-center">
        <slot />
    </div>
</main>

<style lang="postcss">
  :global(html) {
    background-color: rgb(30, 32, 48);
  }

  :global(h1) {
		font-family: "Inter Bold";
  }

  :global(h2) {
    font-family: "Inter Italic";
  }

  :global(p, div) {
    font-family: "Inter Regular";
  }
</style>