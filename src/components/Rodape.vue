<template>
  <footer class="rodape">Projeto fictício sem fins comerciais.</footer>
</template>

<style scoped>
.rodape {
  display: flex;
  padding: 1.5rem 7.5rem;
  justify-content: center;
  align-items: center;
  background-color: var(--verde-medio);
}

@media only screen and (max-width: 1300px) {
  .rodape {
    padding: 1.5rem 3.75rem;
  }
}

@media only screen and (max-width: 767px) {
  .rodape {
    padding: 1.5rem;
  }
}
</style>