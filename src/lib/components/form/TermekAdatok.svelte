<script>
  import BizonylatFeltoltese from './BizonylatFeltoltese.svelte';
</script>

<div class="flex md:justify-center md:flex-row flex-col mt-10">
  <div class="flex justify-center text-white">
    <div class="md:w-96">
      <div>
        <label class="markerfield text-2xl tracking-wide" for="product">
          MELYIK TERMÉKKEL JÁTSZOL?</label
        >

        <select
          id="product"
          name="product"
          class="border-[#16a5da] cursor-pointer rounded-xl px-8 py-4 border-[3px] text-xl w-60 block mb-2"
          required
        >
          <option class="text-gray-500" value="" disabled selected>Válassz terméket</option>
          <option class="text-[#003366]" value="termek1">Termék1</option>
          <option class="text-[#003366]" value="termek2">Termék2</option>
          <option class="text-[#003366]" value="termek3">Termék3</option>
          <option class="text-[#003366]" value="termek4">Termék4</option>
          <option class="text-[#003366]" value="termek5">Termék5</option>
          <option class="text-[#003366]" value="termek6">Termék6</option>
          <option class="text-[#003366]" value="termek7">Termék7</option>
        </select>
      </div>
      <div>
        <label class="markerfield text-2xl tracking-wide" for="ap_code">AP KÓD*</label>
        <input
          class="border-[#16a5da] rounded-xl px-8 py-4 border-[3px] text-xl w-60 block mb-2"
          type="text"
          id="ap_code"
          name="ap_code"
          placeholder="AP A_ _ _ _ _ _ _ _ _"
          maxlength="30"
          required
        />
      </div>
      <div>
        <label class="markerfield text-2xl tracking-wide" for="date">VÁSÁRLÁS DÁTUMA*</label>
        <input
          class="border-[#16a5da] rounded-xl px-8 py-4 border-[3px] text-xl w-60 block mb-2"
          type="date"
          id="date"
          name="date"
          required
        />
      </div>
      <div class="full-width">
        <label class="markerfield text-2xl tracking-wide" for="time">VÁSÁRLÁS IDŐPONTJA*</label>
        <input
          class="border-[#16a5da] rounded-xl px-8 py-4 border-[3px] text-xl w-60 block mb-2"
          type="time"
          id="time"
          name="time"
          required
        />
      </div>

      <BizonylatFeltoltese />
      <!-- <div class="sm:block flex flex-col justify-center mb-8">
        <label
          for="receipt_upload"
          class="mb-2 w-60 block text-center mt-8 markerfield text-2xl py-4 text-white bg-[#003366] tracking-widest border-[#16a5da] border-4 rounded-xl hover:cursor-pointer hover:border-[#16a5da]"
          >BIZONYLAT FELTÖLTÉSE</label
        >
        <input type="file" id="receipt_upload" class="hidden" name="receipt_upload" />
      </div> -->
    </div>
  </div>
  <!-- terms -->
  <div class="flex justify-center sweetSansRegular text-white text-[16px]! px-2">
    <!-- <img
                class="absolute w-[200px] top-0 right-[-300px] xl:block hidden"
                src="{% static 'assets/figura_jobb.svg' %}"
                alt="figura"
              /> -->
    <div class="md:w-96 mx-atuo">
      <p>
        A *-gal jelölt mezők kitöltése kötelező.<br />A többi adat megadása segíti a nyeremény gyors
        eljuttatását!
      </p>
      <div class="flex items-start mt-8">
        <input
          type="checkbox"
          id="accept-rules"
          name="accept-rules"
          class="min-h-5 min-w-5 mt-2 text-red-600 rounded accent-red-600 checked:bg-red-600 focus:outline-none cursor-pointer focus:ring-0"
          required
        />
        <label class="ml-4" for="accept-rules"></label>
        <p>Elfogadom a játékszabályzatot*</p>
      </div>
      <div class="flex items-start mt-8">
        <input
          type="checkbox"
          id="accept-terms"
          name="accept-terms"
          class="min-h-5 min-w-5 mt-2 text-red-600 rounded accent-red-600 checked:bg-red-600 focus:outline-none cursor-pointer focus:ring-0"
          required
        />
        <label class="ml-4" for="accept-terms"></label>
        <p>
          Elfogadom az
          <a target="_blank" href="" class="underline">adatvédelmi szabályzatot</a>*
        </p>
      </div>
      <div class="flex items-start mt-8">
        <input
          type="checkbox"
          id="accept_info_share"
          name="accept_info_share"
          class="min-h-5 min-w-5 mt-2 text-red-600 rounded accent-red-600 checked:bg-red-600 focus:outline-none cursor-pointer focus:ring-0"
          required
        />
        <label class="ml-4" for="accept_info_share"></label>
        <p>
          Hozzájárulok, hogy személyes adataimat a Szervező további kommunikációk kapcsán kezelje.*
        </p>
      </div>

      <div
        class="g-recaptcha mt-4"
        // data-sitekey="{{ RECAPTCHA_PUBLIC_KEY }}"
      ></div>

      <!---------------->
      <div class="flex justify-center">
        <input
          class="w-60 markerfield text-2xl PodravkaSans-Bold py-4 bg-[#16a5da] mt-12 mb-8 tracking-widest border-[#002447] border-4 rounded-xl hover:cursor-pointer text-white"
          type="submit"
          value="BEKÜLDÉS"
        />
      </div>
    </div>
  </div>
</div>
