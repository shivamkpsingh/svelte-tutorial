<script>
  export let showModal = false;
  let isPromo = true;
</script>

<main>
  {#if showModal}
    <div class="backdrop" class:promo={isPromo} on:click|self>
      <div class="modal">
        <slot></slot>
      </div>
    </div>
  {/if}
</main>

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.8);
  }
  .modal {
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    text-align: center;
    background-color: white;
  }
  .modal {
    background: crimson;
    color: white;
  }
</style>
