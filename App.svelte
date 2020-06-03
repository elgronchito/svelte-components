<script>
  import Modal from "./components/Modal.svelte";
  import SomeBox from "./components/SomeBox.svelte";

  let showModal = false;
  $: console.log("showModal", showModal);

  function toggleModal() {
    console.log("click");
    showModal = !showModal;
  }
</script>

<style>
  :root {
    --theme-background: #f1f1f1;
    --theme-primary: #cf0056;
    --theme-secondary: #ff5a00;
  }

  main {
    font-family: sans-serif;
    text-align: center;
  }
</style>

<main>
	<h1>Mis Componentes</h1>
  
  {#if showModal}
  <Modal bind:visible={showModal} modal={true}> 
    <SomeBox on:close={() => showModal = false}/>
  </Modal>
  {:else}
  <button on:click={toggleModal} >Show Modal</button>
  <p>No visible</p>
  {/if}
</main>