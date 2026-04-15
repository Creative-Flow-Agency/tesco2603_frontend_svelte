<script lang="ts">
  let productChoices = [
    { value: '1', label: 'Product 1' },
    { value: '2', label: 'Product 2' },
    { value: '3', label: 'Product 3' },
  ];

  let selectedProducts: string[] = [];
  let isOpen = false;

  // Toggle item selection
  function handleItemClick(value: string) {
    if (selectedProducts.includes(value)) {
      selectedProducts = selectedProducts.filter((item) => item !== value);
    } else {
      selectedProducts = [...selectedProducts, value];
    }
  }

  // Get button text
  $: buttonText =
    selectedProducts.length > 0 ? `${selectedProducts.length} kiválasztva` : 'Válassz';
</script>

<div>
  <label class="markerfield text-2xl tracking-wide" for="products">MELYIK TERMÉKKEL JÁTSZOL?</label>
  <input type="hidden" name="products" id="products" value={selectedProducts.join(',')} />
</div>
<div class="container">
  <button type="button" class="select-btn" class:open={isOpen} on:click={() => (isOpen = !isOpen)}>
    <span class="product-text">{buttonText}</span>
    <svg
      class="w-10"
      width="800px"
      height="40px"
      viewBox="0 0 24 24"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M7 10L12 15L17 10"
        stroke="#999fa2"
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
  </button>
  <ul class="list-items">
    {#each productChoices as item}
      <li>
        <button
          type="button"
          class="product"
          class:checked={selectedProducts.includes(item.value)}
          on:click={() => handleItemClick(item.value)}
          role="option"
          aria-selected={selectedProducts.includes(item.value)}
        >
          <span class="checkbox">
            <i class="fa-solid fa-check check-icon"></i>
          </span>

          <span class="item-text" data-value={item.value}>
            {item.label}
          </span>
        </button>
      </li>

      <hr class="my-1 w-full bg-[#cbd6e072]" />
    {/each}
  </ul>
</div>

<style>
  .select-btn {
    width: 15rem;
    display: flex;
    height: 4rem;
    align-items: center;
    justify-content: space-between;
    padding-right: 16px;
    padding-left: 28px;
    border-radius: 12px;
    border: 3px solid #16a5da;
    cursor: pointer;
    background-color: transparent;
  }
  .select-btn .btn-text {
    font-size: 17px;
    font-weight: 400;
    color: #333;
  }
  .select-btn.open svg {
    transform: rotate(-180deg);
  }
  .list-items {
    width: 20rem;
    margin-top: 15px;
    margin-bottom: 15px;
    border-radius: 8px;
    padding: 16px;
    background-color: #fff;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
    display: none;
    height: 200px;
    overflow-y: auto;
  }
  .select-btn.open ~ .list-items {
    display: block;
  }
  .list-items .product,
  .parlour_candy_product {
    display: flex;
    align-items: center;
    justify-content: left;
    list-style: none;
    height: auto;
    cursor: pointer;
    transition: 0.3s;
    padding: 0 5px;
    border-radius: 8px;
  }
  .list-items .product:hover,
  .parlour_candy_product:hover {
    background-color: #cbd6e072;
  }
  .product .item-text,
  .parlour_candy_product .item-text {
    max-width: 220px;
    font-size: 16px;
    font-weight: 400;
    color: #333;
  }
  .product .checkbox,
  .parlour_candy_product .checkbox {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 16px;
    width: 16px !important;
    border-radius: 4px;
    margin-right: 12px;
    border: 1.5px solid #c0c0c0;
    transition: all 0.3s ease-in-out;
  }
  .product.checked .checkbox,
  .parlour_candy_product.checked .checkbox {
    background-color: #203e7e;
    border-color: #203e7e;
  }
  .checkbox .check-icon {
    color: #fff;
    font-size: 11px;
    transform: scale(0);
    transition: all 0.2s ease-in-out;
  }
  .product.checked .check-icon,
  .parlour_candy_product.checked .check-icon {
    transform: scale(1);
  }
</style>
