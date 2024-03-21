<template>
  <main>
    <div class="container">
      <form :onsubmit="teste">
        <div class="form-content">

          <div class="data">
            <label for="email">E-mail</label>
            <input type="email" name="email" v-model="steps.email" id="email" placeholder="E-mail">
          </div>

          <div class="data">
            <label for="body">Conteúdo do E-mail</label>
            <textarea name="body" id="body" v-model="steps.body" cols="30" rows="8" r
              placeholder="Digite o conteúdo do e-mail"></textarea>
          </div>

        </div>
        <div class="container-button">
          <button type="submit" :disabled="!validateForm">ENVIAR</button>
        </div>
      </form>
    </div>
  </main>
</template>

<script setup lang="ts">
import { computed, reactive } from 'vue';

const steps = reactive({
  email: '',
  body: ''
})

const teste = (event: Event) => {
  event.preventDefault()
  alert(`E-mail: ${steps.email}, conteúdo: ${steps.body}`);
  Object.assign(steps, {
    body: '', email: ''
  })
}

const validateForm = computed(() => {
  const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/i

  return !!steps.email.trim() && !!steps.body.trim() && steps.body.trim().length > 5 && regex.test(steps.email)
})
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

.container {
  background-color: var(--color-background-mute);
  box-shadow: 2px 4px 2px 2px var(--color-border);
  border-radius: 12px;
  height: 420px;
  width: 520px;
}

.container form {
  flex-direction: column;
  padding: 4rem 2rem;
  display: flex;
  height: 100%;
  width: 100%;
  gap: 2em;
}

.container form .container-button {
  justify-content: center;
  align-self: center;
  display: flex;
}

.container form .container-button button {
  border-radius: 4px;
  font-weight: bold;
  width: 120px;
  height: 30px;
  color: #ffffff;
  border: 0 none;
  background-color: var(--color-backgroud-btn);
}

.container form .container-button button:hover {
  border-radius: 4px;
  width: 120px;
  height: 30px;
  color: #76ABAE;
  background-color: var(--color-background);
}

.container form .container-button button:disabled {
  border-radius: 4px;
  width: 120px;
  height: 30px;
  color: #ffffff;
  background-color: gray;
}

.container .form-content {
  flex-direction: column;
  display: flex;
  gap: 1em;
}

.container .form-content .data {
  flex-direction: column;
  display: flex;
}

.container .form-content .data label {
  color: var(--color-text);
  font-weight: bold;
  width: 100%;
  float: left;
}

.container .form-content .data label:after {
  content: ": "
}

.container .form-content .data textarea {
  background-color: var(--color-background-soft);
  color: var(--color-text);
  border-radius: 4px;
  padding: 8px;
  max-height: 180px;
  min-height: 40px;
  max-width: 100%;
  min-width: 100%;
  height: 100%;
  width: 100%;
  box-shadow: 0 0 0 0;
  border: 0 none;
  outline: 0;
}

.container .form-content .data textarea:focus {
  border: 1px solid rgb(0, 104, 104);
  outline: none;
}

.container .form-content .data input {
  background-color: var(--color-background-soft);
  color: var(--color-text);
  border-radius: 4px;
  padding: 8px;
  max-width: 100%;
  min-width: 100%;
  max-height: 180px;
  height: 100%;
  width: 100%;
  box-shadow: 0 0 0 0;
  border: 0 none;
  outline: 0;
}

.container .form-content .data input:focus {
  border: 1px solid rgb(0, 104, 104);
  outline: none;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
