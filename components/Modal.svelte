<script>
  import { fade } from "svelte/transition";
  export let modal = true;
  export let visible = true;

  const handleBgClick = () => {
    if (!modal) {
      visible = false;
    }
  };

  const handleClose = () => {
    visible = false;
  };
</script>

<style>
  .container {
    position: fixed;
    top: 0;
    left: 0;
    display: none;
    flex-flow: column;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0);
  }
  .visible {
    display: flex;
  }
</style>

<div class:visible = {visible} transition:fade class="container" on:click={handleBgClick}>      
    <slot></slot>
</div>
