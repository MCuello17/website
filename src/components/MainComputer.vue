<template>
  <main :id="mobile ? 'mobile-view' : 'desktop-view'">
      <section id="screen" class="cut-corner">
          <h1 class="title">
              Test Title
          </h1>
          <div class="icon"></div>
      </section>
  </main>
</template>

<script>
export default {
  name: 'MainComputer',
  data () {
    return {
      mobile: window.innerWidth <= 992
    }
  },
  created () {
    addEventListener('resize', () => {
      this.mobile = innerWidth <= 992
    })
  }
}
</script>

<style>
    #mobile-view,
    #desktop-view {
        height: 100vh;
        width: 100vw;
        overflow: hidden;
        background-color: var(--background);
        color: var(--primary);
        padding: 25px;
        display: flex;
        flex-direction: column;
    }

    #screen {
        position: relative;
        height: 100%;
        width: 100%;
        flex-grow: 1;
        border: 2px solid var(--primary);
        padding: 20px;
        display: grid;
        grid-gap: 5px;
        justify-content: center;
        grid-template-columns: repeat(auto-fill, 90px);
        grid-auto-rows: 90px;
    }

    #screen:before,
    #screen:after {
        position: fixed;
    }

    #screen:before {
        bottom: 27px;
        left: 27px;
    }

    #screen:after {
        bottom: 25px;
        left: 25px;
    }

    #desktop-view #screen {
        overflow: hidden;
    }

    #mobile-view #screen {
        overflow-y: scroll;
    }

    .title {
        grid-column: 1 / -1;
    }

    .icon {
        border: 1px solid #fff;
    }
</style>
