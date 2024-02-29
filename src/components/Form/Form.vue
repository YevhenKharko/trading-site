<script>
export default {

  data() {
    return {
      name: '',
      email: '',
      message: '',
      showModal: false,
    };
  },

  methods: {
    handleSubmit(e) {
      e.stopPropagation();

      if (this.validateForm()) {
        e.preventDefault();
        this.resetForm();
        this.showModal = true;
      }
    },

    validateForm() {
      return this.name.length !== 0 && this.email.length !== 0;
    },

    resetForm() {
      this.name = '';
      this.email = '';
      this.message = '';
    },
    closeModal() {
      this.showModal = false;
    },
  },
}

</script>


<template>
  <form action="" class="form">
    <div class="info">
      <h2 class="title" id="contact">Contact us!</h2>
      <p>The support staff and customer service are available to help you with any questions or needs you might have. Just
        drop us a line.</p>

      <p>This site is owned and operated by Kode Tech Solutions LTD</p>
      <div>
        <label for="phone">Phone:</label>
        <span id="phone">442038857261</span>
      </div>

      <div>
        <label for="email">Email:</label>
        <span id="email">help@google.com</span>
      </div>

      <div>
        <label for="address">Address:</label>
        <span id="address">Trust Company Complex, Ajeltake Road, Ajeltake Island, Majuro, Republic of the Marshall Islands,
          MH 96960</span>
      </div>
    </div>
    <div class="field">
      <input type="text" v-model="name" required placeholder="Name">
      <input type="email" v-model="email" required placeholder="Email">
      <textarea v-model="message" placeholder="Message"></textarea>
      <button type="submit" @click="handleSubmit">Send</button>
    </div>
    <div v-if="showModal" class="modal">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <p class="modal-msg">Your message has been sent!</p>
      </div>
    </div>
  </form>
</template>

<style lang="scss">
.form {
  display: grid;
  grid-column: 1 / -1;

  @media (min-width: 768px) {
    grid-column: 2 / -2;
  }

  @media (min-width: 1200px) {
    grid-column: 1 / -1;
  }

  .info {
    margin-bottom: 32px;

    @media (min-width: 1200px) {
      grid-column: 1 / 5;
      max-width: 480px;
    }

    &:first-child p {
      margin-bottom: 32px;
    }

    &:not(:last-child) span {
      margin-bottom: 16px;
    }
  }
}

.title {
  display: grid;
  grid-column: 1 / 2;
  font-size: 40px;
  font-family: 'Museo Moderno';
  font-weight: 700;
  color: #333;
  margin-bottom: 32px;

  @media (min-width: 768px) {
    font-size: 58px;
    max-width: 500px;
  }
}

label {
  display: block;
  font-family: 'Museo Sans';
  font-weight: 700;
  margin-bottom: 8px;
  font-size: 15px;
}

span {
  display: block;
  font-size: 16px;
  font-family: 'Montserrat';
}

p {
  font-size: 18px;
  font-family: 'Montserrat';
}

.field {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 48px 16px;
  gap: 24px;


  @media (min-width: 1200px) {
    grid-column: 6 / 12;
    padding: 80px;
    max-width: 470px;
  }

  input,
  textarea {
    height: 40px;
    font-size: 16px;
    font-family: 'Montserrat';
    padding: 7px 16px;
    border: 2px solid #828282;
    width: 100%;
    transition: border 0.4s ease;
    border-radius: 3px;

    &:hover {
      cursor: pointer;
    }

    &:focus,
    &:active {
      border: 2px solid #000;
    }
  }

  textarea {
    height: 90px;
  }

  button {
    margin-top: 24px;
    font-family: 'Museo Sans';
    font-weight: 700;
    color: #fff;
    text-transform: uppercase;
    background-color: #6248ff;
    height: 54px;
    width: 180px;
    border-radius: 60px;
  }
}

.modal {
  display: flex;
  align-items: center;
  justify-content: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 1;

  &-content {
  background-color: #fff;
  padding: 20px;
  font-weight: 700;
  border-radius: 8px;
  max-width: 500px;
  text-align: center;
  }

  &-msg {
  font-family: 'Museo Sans';
  font-weight: 700;
  font-size: 36px;
  }
}




.close {
  width: 32px;
  height: 32px;
  cursor: pointer;
  position: relative;
  top: -20px;
  right: -95%;
  font-size: 32px;
}
</style>
