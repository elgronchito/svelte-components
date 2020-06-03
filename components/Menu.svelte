<script>
  import { fade } from "svelte/transition";
  export let items;
</script>

<style>
  .container {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    flex-flow: column;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0);
  }

  .inner-container {
    width: 80%;
    min-height: 100px;
    background-color: #a0a0a0;
  }

  ul {
    padding: 0;
    list-style: none;
    border: 1px solid green;
  }

  li {
    text-decoration: none;
    margin: 4px;
    background-color: blueviolet;
  }
</style>

<div transition:fade class="container">

  <div class="inner-container">
    <ul>
      {#each items as item, i}
        <li>{item.text}</li>
      {/each}
    </ul>
  </div>

</div>
<!-- 
  const menuItems = [
    {
      id: "opcion1",
      text: "Menu Opcion Aaa",
      action: () => console.log("Menu element Option A")
    },
    {
      id: "opcion2",
      text: "Menu Opcion B",
      action: () => console.log("Menu element Option B")
    },
    {
      id: "opcion3",
      text: "Menu Opcion C",
      action: () => console.log("Menu element Option C")
    }
  ]; -->