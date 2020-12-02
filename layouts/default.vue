<template>
  <div class="box">
    <div class="head">
      <div class="pages">
        <NuxtLink v-for="(_, key) in Array(3)" :key="key" to="nothing-here" class="link">
          Пустая страница {{ key+1 }}
        </NuxtLink>
      </div>
      <NuxtLink class="logo" to="/">
        Табунодел
      </NuxtLink>
      <div class="motto">
        Создай свой собственный гарем из обворожительных кобылок
      </div>
    </div>
    <div class="body">
      <Nuxt />
    </div>
  </div>
</template>

<style lang="scss">
.box{
  max-width: 1400px;
  padding: 0 40px;
}
.head{
  height: 180px;
  margin-bottom: 100px;
  .pages{
    float: left;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    margin-right: 60px;
    .link{
      font-size: 28px;
      font-weight: bold;
      text-transform: uppercase;
      text-decoration: overline;
      display: block;
      color: orange;
      &:first-of-type{
        text-decoration: none;
      }
    }
  }
  .logo{
    font-size: 100px;
    font-weight: bold;
    text-transform: uppercase;
    color: inherit;
    text-decoration: none;
  }
  .motto{
    font-size: 24px;
    color: dimgray;
    font-weight: bold;
  }
}

html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
