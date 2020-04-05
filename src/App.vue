<template>
  <div id="app" class="flex-container">
    <header>
      <nav id="nav">
        <router-link to="/">Home</router-link>|
        <router-link to="/about">About</router-link>
      </nav>
      Header
    </header>
    <main>
      <aside>
        <nav id="nav">
          <router-link to="/">Home</router-link>|
          <router-link to="/about">About</router-link>
        </nav>
      </aside>
      <section>
        <router-view />
      </section>
    </main>
  </div>
</template>

<style lang="scss">
* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
.flex-container {
  height: 100%;
}

main {
  display: flex;
  border: 1px solid red;
  height: 90vh;
  overflow-y: hidden;
}

header {
  background-color: #dedede;
  height: 10vh;
  padding: 10px;
  border-radius: 2px;
}

/* Create two unequal columns that sits next to each other */
/* Sidebar/left column */
aside {
  flex: 10%;
  background-color: #f1f1f1;
  padding: 10px;
  border-radius: 2px;
  min-width: 130px;
  box-shadow: 0 2px 2px 2px #dedede;
}
@media only screen and (max-width: 600px) {
  aside {
    display: none;
    transition: display 2s;
  }
}

/* Main column */
section {
  flex: 80%;
  padding: 10px;
  border-radius: 2px;
  height: inherit;
  overflow-y: auto;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
