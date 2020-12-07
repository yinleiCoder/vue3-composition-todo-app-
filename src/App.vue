<template>
  <main>
    <div class="container">
      <h1>Welcome to use Vue3.0 Todo APP.</h1>
      <div class="input-add">
        <input type="text" name="todo"/>
        <button>
          <i class="plus"></i>
        </button>
      </div>
      <div class="filters">
        <span class="filter active">All</span>
        <span class="filter">Undone</span>
        <span class="filter">Done</span>
      </div>
      <div class="todo-list">
        <div class="todo-item">
          <label>
            <input type="checkbox"/>
            给王可尔说句我爱你
            <span class="check-button"></span>
          </label>
        </div>
        <div class="todo-item">
          <label>
            <input type="checkbox"/>
            给王可尔说“祝你幸福”
            <span class="check-button"></span>
          </label>
        </div>
        <div class="todo-item">
          <label>
            <input type="checkbox"/>
            给王可尔说“you complete me.”
            <span class="check-button"></span>
          </label>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
