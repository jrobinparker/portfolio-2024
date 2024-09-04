<script>
  import "../app.css";
</script>

<slot />

<style lang="postcss">
  :global(html) {
    background-color: theme(colors.stone.900);
    overflow: hidden;
    font-family: 'Helvetica Neue';
  }
</style>