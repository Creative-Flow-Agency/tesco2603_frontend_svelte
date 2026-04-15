<script>
  import SzemelyesAdatok from './form/SzemelyesAdatok.svelte';
  import TermekAdatok from './form/TermekAdatok.svelte';

  let formType = 'none';
</script>

<section class="relative bg-[#003366] rounded-xl -mt-[5vw] pt-[3vw]">
  <h2
    class="markerfield text-[#F8E300] lg:text-[4vw] text-[8vw] text-center leading-[3vw] pt-[10vw]"
  >
    HOGYAN SZERETNÉL JÁTSZANI?
  </h2>
  <div class="flex md:gap-12 gap-4 md:mb-0 mb-4 md:flex-row flex-col justify-center mt-12 px-12">
    <button
      on:click={() => (formType = 'guest')}
      id="guestBtn"
      class="rounded-xl tracking-widest! p-4 text-xl border-2 border-[#002447] shadow-lg text-white markerfield bg-[#008ed0]"
    >
      VENDÉGKÉNT JÁTSZOM
    </button>

    <button
      on:click={() => (formType = 'login')}
      id="loginBtn"
      class="rounded-xl tracking-widest! p-4 text-xl border-2 border-[#002447] shadow-lg text-white markerfield bg-[#b4cc06]"
    >
      BEJELENTKEZEM
    </button>
  </div>
  <!-- vendégként játszom -->
  <div class:hidden={formType !== 'guest'} class="hidden mt-4">
    <div class="sm:w-auto w-[95vw]">
      <form
        id="submissionForm"
        method="POST"
        class="mt-8"
        enctype="multipart/form-data"
        // onsubmit="onSubmit(event)"
        on:submit={onsubmit}
      >
        <h2 class="text-center text-[#F8E300] lg:text-[4vw] text-[8vw] mb-12 markerfield md:pt-10">
          KÓDBEKÜLDÉS
        </h2>

        <SzemelyesAdatok />
        <TermekAdatok />
      </form>
    </div>
  </div>
  <!-- bejelentkezem -->
  <div class:hidden={formType !== 'login'} class="hidden mt-4">
    <div class="sm:w-auto w-[95vw]">
      <form
        id="submissionForm"
        method="POST"
        class="mt-8"
        enctype="multipart/form-data"
        on:submit={onsubmit}
      >
        <h2 class="text-center text-[#F8E300] lg:text-[4vw] text-[8vw] mb-12 markerfield md:pt-10">
          KÓDBEKÜLDÉS
        </h2>

        <TermekAdatok />
      </form>
    </div>
  </div>
  <img
    src="assets/also képek.png"
    alt="Tibi csokik, figura blokkal a kezében"
    class="w-[60vw] ml-auto"
  />
</section>
