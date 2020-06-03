<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  const handleClose = () => {
    console.log("dispatch close..");
    dispatch("close");
  };
</script>

<style>
  div {
    display: inline-block;
    width: 200px;
    height: 100px;
    background: var(--theme-background, pink);
    border: 1px solid var(--theme-primary);
    box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.1);
  }

  p {
    text-align: center;
    margin: auto;
  }
</style>

<div>
  <p>Hola Mundo</p>
  <button on:click="{handleClose}">Close</button>
</div>