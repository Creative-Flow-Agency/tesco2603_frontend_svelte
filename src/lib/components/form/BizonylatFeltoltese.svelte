<script lang="ts">
  let files: FileList | null = null;
  let error = '';
</script>

<div class="sm:block flex flex-col justify-center mb-8">
  <label
    for="receipt_upload"
    class="mb-2 w-60 block text-center mt-8 markerfield text-2xl py-4 text-white bg-[#003366] tracking-widest border-[#16a5da] border-4 rounded-xl hover:cursor-pointer"
  >
    BIZONYLAT FELTÖLTÉSE
  </label>

  <input
    type="file"
    id="receipt_upload"
    name="receipt_upload"
    class="hidden"
    required
    bind:files
    on:change={() => {
      error = '';

      if (files && files.length > 0) {
        const file = files[0];

        // if (file.size > 2_000_000) {
        //   error = 'A fájl túl nagy (max 2MB)';
        // }
      }
    }}
  />

  {#if files && files.length > 0 && !error}
    <p class="upload-success text-green-500 font-bold mt-2 text-center">
      Fájl sikeresen kiválasztva!
    </p>
  {/if}

  {#if error}
    <p class="text-red-700 font-bold mt-2 text-center">
      {error}
    </p>
  {/if}
</div>
