<template>
  <main>
    <div class="container">
      <form>
        <div class="form-content">

          <div class="data">
            <label for="email">E-mail</label>
            <input type="email" name="email" id="email" placeholder="E-mail">
          </div>

          <div class="data">
            <label for="body">Conteúdo do E-mail</label>
            <textarea name="body" id="body" cols="30" rows="8" r placeholder="Digite o conteúdo do e-mail"></textarea>
          </div>

        </div>
        <div class="container-button">
          <button type="submit">Envair</button>
        </div>
      </form>
    </div>
  </main>
</template>

<script setup lang="ts">
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
  width: 90px;
  height: 30px;
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
  color: var(--color-text);
  max-width: 100%;
  min-width: 100%;
  max-height: 180px;
  height: 100%;
  width: 100%;
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
