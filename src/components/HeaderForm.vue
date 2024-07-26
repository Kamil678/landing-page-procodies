<template>
  <div class="form-container">
    <p>Enter details</p>
    <form>
      <div class="name-container">
        <input
          type="text"
          name="firstName"
          placeholder="First name"
          aria-label="First name"
        />
        <input
          type="text"
          name="lastName"
          placeholder="Last name"
          aria-label="Last name"
        />
      </div>
      <input
        type="text"
        name="street"
        placeholder="Street"
        aria-label="Street"
      />
      <div class="adress-container">
        <input
          type="text"
          name="postalCode"
          placeholder="Postal code"
          aria-label="Postal code"
          pattern="[0-9]{2}-[0-9]{3}"
        />
        <input type="text" name="city" placeholder="City" aria-label="City" />
      </div>
      <input
        type="tel"
        name="phoneNumber"
        placeholder="Phone number"
        aria-label="Phone number"
        pattern="\+?[0-9\s\-\(\)]{7,}"
      />
      <input
        type="email"
        name="email"
        placeholder="E-mail"
        aria-label="E-mail"
      />
      <button type="button">Proceed to payment</button>
    </form>
    <div class="form-footer">
      <img
        src="../assets/mc-affe-secure.png"
        alt="McAffe Secure"
        width="93"
        height="40"
      />
      <img
        src="../assets/truste-verified.png"
        alt="Truste verified"
        width="93"
        height="40"
      />
      <img src="../assets/ssl.png" alt="SSL 256 BIT" width="93" height="40" />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style lang="scss">
.form-container {
  border: 1px solid #dbdbdb;
  border-radius: 20px;
  padding: 24px 23.5px;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 24px 0;

  p {
    font-size: 32px;
    font-weight: 500;
    line-height: 37.5px;
    text-align: center;
  }

  form {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 16px 0;

    .name-container,
    .adress-container {
      display: flex;
      align-items: center;
      gap: 0 16px;
    }

    input {
      width: 100%;
      height: 48px;
      border: 1px solid #2d473e;
      border-radius: 10px;
      font-size: 16px;
      font-weight: 400;
      line-height: 24px;
      text-align: left;
      padding-left: 16px;
    }

    button {
      border: none;
      background-color: #006340;
      padding: 12px 16px 12px 16px;
      border-radius: 10px;
      text-transform: uppercase;
      color: #fff;
      cursor: pointer;
      font-size: 16px;
      font-weight: 600;
      line-height: 24px;
    }
  }

  .form-footer {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0 16px;
  }
}
</style>
