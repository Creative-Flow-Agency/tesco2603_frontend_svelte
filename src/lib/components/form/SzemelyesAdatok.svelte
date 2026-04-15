<div class="text-blue sweetSansRegular mb-[5vw]">
  <div class="flex justify-center md:flex-row flex-col">
    <div class="relative md:mx-0 mx-auto">
      <p class="text-3xl text-[#de0b15] absolute top-0 right-2">*</p>
      <label for="first_name"></label>
      <input
        class="bg-white border-[#16A5DA] rounded-xl px-8 py-4 border-[3px] text-xl w-60"
        type="text"
        id="first_name"
        name="first_name"
        placeholder="Vezetéknév"
        maxlength="30"
        required
      />
    </div>
    <div class="relative md:mx-8 md:my-0 my-8 mx-auto">
      <p class="text-3xl text-[#de0b15] absolute top-0 right-2">*</p>
      <label for="second_name"></label>
      <input
        class="bg-white border-[#16A5DA] rounded-xl px-8 py-4 border-[3px] text-xl w-60"
        type="text"
        id="second_name"
        name="second_name"
        placeholder="Keresztnév"
        maxlength="30"
        required
      />
    </div>
    <div class="relative md:mx-0 mx-auto">
      <p class="text-3xl text-[#de0b15] absolute top-0 right-2">*</p>
      <label for="age"></label>
      <input
        class="bg-white border-[#16A5DA] rounded-xl px-8 py-4 border-[3px] text-xl w-60"
        type="number"
        id="age"
        name="age"
        min="18"
        max="120"
        placeholder="Életkor"
        required
      />
    </div>
  </div>
  <div class="flex mt-8 justify-center md:flex-row flex-col">
    <div class="relative md:mx-0 mx-auto">
      <p class="text-3xl text-[#de0b15] absolute top-0 right-2">*</p>
      <label for="email"></label>
      <input
        class="bg-white border-[#16A5DA] rounded-xl px-8 py-4 border-[3px] text-xl w-60"
        type="email"
        id="email"
        name="email"
        placeholder="Email cím"
        required
      />
    </div>
    <div class="md:mx-8 mx-auto md:my-0 my-8">
      <label for="telephone"></label>
      <input
        class="bg-white border-[#16A5DA] rounded-xl px-8 py-4 border-[3px] text-xl w-60"
        type="tel"
        id="telephone"
        name="telephone"
        placeholder="Telefonszám"
        pattern="(\+?\d{11})"
      />
    </div>
    <div class="relative md:mx-0 mx-auto">
      <p class="text-3xl text-[#de0b15] absolute top-0 right-2">*</p>
      <label for="postal_code"></label>
      <input
        class="bg-white border-[#16A5DA] rounded-xl px-8 py-4 border-[3px] text-xl w-60"
        type="number"
        id="postal_code"
        name="postal_code"
        placeholder="Irányítószám"
        pattern="[0-9]{4}"
        required
      />
    </div>
  </div>
</div>
