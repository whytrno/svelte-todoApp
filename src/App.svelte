<script>
  let task = ''
  let todos = []
  function addTodo() {
    todos.push({task})
    todos = todos
    task = ''
  }
  function removeTodo(i) {
    todos.splice(i, 1)
    todos = todos
  }
</script>
<div class="w-1/3 mx-auto my-10">
  <form on:submit|preventDefault={addTodo} class="space-x-5 border-b pb-5 border-blue-700 flex justify-between">
    <input type="text" required bind:value={task} placeholder="Masukkan tugasmu disini" class="border border-blue-700 py-3 px-5 rounded-lg w-full">
    <button type="submit" class="py-3 px-5 bg-blue-700 w-min whitespace-nowrap text-white rounded-lg">Add task</button>
  </form>
  <div class="my-5 space-y-2">
    {#each todos as todo, i}
      <button on:click={() => removeTodo(i)} class="group flex items-center justify-between hover:border-red-700 hover:text-red-700 py-3 px-5 border border-blue-700 rounded-lg text-blue-700 w-full text-start">{i + 1}. {todo.task} <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-0 h-0 group-hover:w-5 group-hover:h-5">  <path stroke-linecap="round" stroke-linejoin="round" d="M14.74 9l-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 01-2.244 2.077H8.084a2.25 2.25 0 01-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 00-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 013.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 00-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 00-7.5 0" /></svg>
      </button>
    {/each}
  </div>
</div>