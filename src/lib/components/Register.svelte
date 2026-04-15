<script lang="ts">
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  let isOpen = false;
  let email = '';
  let password = '';
  let confirmPassword = '';

  function openPopup() {
    isOpen = true;
  }

  function closePopup() {
    isOpen = false;
    email = '';
    password = '';
    confirmPassword = '';
  }

  function handleSubmit() {
    // Dispatch register event with credentials
    dispatch('register', { email, password, confirmPassword });
    closePopup();
  }

  function handleKeydown(event: KeyboardEvent) {
    if (event.key === 'Escape') {
      closePopup();
    }
  }
</script>

<svelte:window on:keydown={handleKeydown} />

<!-- Trigger Button -->
<button on:click={openPopup} type="button" class="bg-[#008ed0] px-2 rounded-full text-white">
  REGISZTRÁCIÓ
</button>

<!-- Animated Popup Modal -->
{#if isOpen}
  <div class="modal-overlay" on:click={closePopup}>
    <div class="modal-content" on:click|stopPropagation>
      <div class="modal-header">
        <h2>Regisztráció</h2>
        <button class="close-btn" on:click={closePopup} type="button" aria-label="Bezárás">
          ✕
        </button>
      </div>

      <form class="register-form" on:submit|preventDefault={handleSubmit}>
        <div class="form-group">
          <label for="email">Email cím</label>
          <input type="email" id="email" bind:value={email} placeholder="pelda@email.hu" required />
        </div>

        <div class="form-group">
          <label for="password">Jelszó</label>
          <input
            type="password"
            id="password"
            bind:value={password}
            placeholder="Jelszó"
            required
          />
        </div>

        <div class="form-group">
          <label for="confirmPassword">Jelszó megerősítése</label>
          <input
            type="password"
            id="confirmPassword"
            bind:value={confirmPassword}
            placeholder="Jelszó megerősítése"
            required
          />
        </div>

        <button
          type="submit"
          class="submit-btn tracking-widest! rounded-xl p-4 text-2xl border-2 border-[#002447] shadow-lg text-white markerfield bg-[#008ed0] w-full"
          disabled={!email || !password || !confirmPassword}
        >
          REGISZTRÁCIÓ
        </button>
      </form>
    </div>
  </div>
{/if}

<style>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.6);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 9999;
    animation: fadeIn 0.3s ease-out;
  }

  .modal-content {
    background: white;
    border-radius: 16px;
    position: relative;
    z-index: 10000;
    padding: 0;
    max-width: 400px;
    width: 90%;
    max-height: 90vh;
    overflow-y: auto;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
    animation: slideIn 0.3s ease-out;
    transform: scale(0.9);
    animation-fill-mode: forwards;
  }

  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 24px 24px 16px;
    border-bottom: 1px solid #e5e7eb;
  }

  .modal-header h2 {
    margin: 0;
    font-size: 24px;
    font-weight: 700;
    color: #1f2937;
  }

  .close-btn {
    background: none;
    border: none;
    font-size: 24px;
    cursor: pointer;
    color: #6b7280;
    padding: 4px;
    border-radius: 4px;
    transition: all 0.2s ease;
  }

  .close-btn:hover {
    background: #f3f4f6;
    color: #374151;
  }

  .register-form {
    padding: 24px;
  }

  .form-group {
    margin-bottom: 20px;
  }

  .form-group label {
    display: block;
    margin-bottom: 8px;
    font-weight: 600;
    color: #374151;
    font-size: 14px;
  }

  .form-group input {
    width: 100%;
    padding: 12px 16px;
    border: 2px solid #e5e7eb;
    border-radius: 8px;
    font-size: 16px;
    transition: border-color 0.2s ease;
    box-sizing: border-box;
  }

  .form-group input:focus {
    outline: none;
    border-color: #667eea;
    box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
  }

  .form-group input::placeholder {
    color: #9ca3af;
  }

  /* .submit-btn {
    width: 100%;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border: none;
    padding: 14px;
    border-radius: 8px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-top: 8px;
  } */

  .submit-btn:disabled {
    opacity: 0.6;
    cursor: not-allowed;
    transform: none;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @keyframes slideIn {
    from {
      opacity: 0;
      transform: scale(0.9) translateY(-20px);
    }
    to {
      opacity: 1;
      transform: scale(1) translateY(0);
    }
  }
</style>
