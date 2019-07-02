<script>
import Navbar from '../components/Navbar'

export default {
  name: 'Index',
  components: {
    Navbar
  },
  data () {
    return {
      filename: '',
      isUploaded: false,
      transaction: {
        filename: 'example',
        txHash: 'example',
        ipfsHash: 'example',
        contract: 'example'
      }
    }
  },
  methods: {
    onChangeFile (event) {
      this.filename = event.target.value
    },
    onSubmit () {
      this.isUploaded = true
    }
  }
}
</script>

<template>
  <div class="content">
    <navbar />
    <div class="main">
      <img
        class="illust"
        src="../assets/upload.png"
      >
      <div class="form">
        <label class="form__upload">
          <input
            type="file" class="form__file"
            @change="onChangeFile($event)"
          />
          SELECT FILE
        </label>
        <input
          v-if="filename"
          v-model="filename"
          class="form__input"
          disabled
        >
        <input
          v-if="filename"
          type="submit"
          class="form__submit"
          value="UPLOAD"
          @click="onSubmit"
        >
        <button v-if="isUploaded" class="form__reload">RELOAD</button>
      </div>
      <div
        v-if="isUploaded"
        class="table"
      >
        <div class="table__field">
          <div class="table__label">
            Filename
          </div>
          <div class="table__value">
            {{ transaction.filename }}
          </div>
        </div>
        <div class="table__field">
          <div class="table__label">
            IPFS Hash
          </div>
          <div class="table__value">
            {{ transaction.ipfsHash }}
          </div>
        </div>
        <div class="table__field">
          <div class="table__label">
            ETC Contract Address
          </div>
          <div class="table__value">
            {{ transaction.contract }}
          </div>
        </div>
        <div class="table__field">
          <div class="table__label">
            Transaction Hash
          </div>
          <div class="table__value">
            {{ transaction.txHash }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.content {
  width: 100%;
  height: 100%;
}

.main {
  display: flex;
  justify-content: center;

  padding-left: 10rem;
  padding-right: 10rem;

  @media (max-width: 900px) {
    padding-left: 6rem;
    padding-right: 6rem;
  }

  @media (max-width: 600px) {
    padding-left: 3rem;
    padding-right: 3rem;
    display: block;
  }

  @media (max-width: 400px) {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
}

.main {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.illust {
  margin-top: 2rem;
  width: 10rem;
}

.form {
  width: 100%;
  margin-top: 2rem;

  &__file {
    display: none;
  }

  &__upload {
    border: none;
    background: #e9ecef;
    display: inline-block;
    padding: 6px 12px;
    cursor: pointer;
    width: 100%;
    box-sizing: border-box;
    font-size: 1.5rem;
    font-weight: 600;
    padding: 1rem;
    display: flex;
    justify-content: center;
  }

  &__input {
    font-family: 'Montserrat', sans-serif;
    color: black;
    border: none;
    background: #f8f9fa;
    width: 100%;
    font-size: 1.2rem;
    box-sizing: border-box;
    font-size: 1.2rem;
    padding: 0.8rem;
    text-align: center;
  }

  &__submit {
    cursor: pointer;
    width: 100%;
    font-size: 1.5rem;
    padding: 0.8rem;
    border: none;
    color: white;
    font-weight: 800;
    font-family: 'Montserrat', sans-serif;
    background: linear-gradient(to right, #4BB5F8, #8EF6FC);
    text-align: center;
    background-position: center;
  }

  &__reload {
    cursor: pointer;
    width: 100%;
    font-size: 1.5rem;
    padding: 0.8rem;
    border: none;
    color: white;
    font-weight: 800;
    font-family: 'Montserrat', sans-serif;
    background-color: black;
    text-align: center;
    background-position: center;
  }

  &__submit:focus,
  &__reload:focus {
    outline: 0;
  }
}

.table {
  display: table;
  width: 100%;
  margin-top: 1rem;

  &__field {
    display: table-row;
  }

  &__label,
  &__value {
    display: table-cell;
    padding-top: 0.3rem;
    padding-bottom: 0.3rem;
  }

  &__field:not(:last-child) .table__label,
  &__field:not(:last-child) .table__value {
    border-bottom: 1px solid #dee2e6;
  }

  &__label {
    font-size: 1.2rem;
    font-weight: 700;
    color: #343a40;
  }

  &__value {
    text-align: right;
    font-size: 1.1rem;
    color: #495057;
  }
}
</style>
