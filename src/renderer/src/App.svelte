<script lang="ts">
  import './assets/styles/app.css'
  let note = $state('')
  let notes = $state([])
</script>

<div class="topbar">
  <h1 class="label">celeron</h1>
  <div class="minilabel">simple todo list app</div>
</div>
<input bind:value={note} type="text" />
<button
  onclick={() => {
    if (note.trim() === '') return
    notes.push(note)
    note = ''
  }}>New</button
>
<div>
  {#each notes as n, i (i)}
    <span>{n}</span>
    <button
      onclick={() => {
        notes.splice(i, 1)
      }}>delete</button
    > <br />
  {/each}
</div>
