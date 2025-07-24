<script>
    const themes = [
    'abyss','acid','aqua','autumn','black','bumblebee','business','caramellatte','cmyk',
    'coffee','corporate','cupcake','cyberpunk','dark','dim','dracula','emerald','fantasy',
    'forest','garden','halloween','lemonade','light','lofi','luxury','night','nord',
    'pastel','retro','silk','sunset','synthwave','valentine','winter','wireframe'
  ];

  let selectedTheme = 'autumn';

  $: {
    document.documentElement.setAttribute('data-theme', selectedTheme);
  }
  let showModal = false;

  function openModal() {
    showModal = true;
  }

  function closeModal() {
    showModal = false;
  }
</script>

<main class="flex flex-col items-center justify-center min-h-screen bg-base-200 gap-4 p-4">
  <button class="btn btn-primary" on:click={openModal}>
    Open modal window
  </button>
    <select class="select select-bordered" bind:value={selectedTheme}>
      {#each themes as theme}
        <option value={theme}>{theme}</option>
      {/each}
    </select>
  {#if showModal}
    <dialog class="modal modal-open">
      <div class="modal-box">
        <h3 class="font-bold text-lg">Модальное окно</h3>
        <p class="py-4">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        <div class="modal-action">
          <button class="btn" on:click={closeModal}>Закрыть</button>
        </div>
      </div>
    </dialog>
  {/if}
</main>

