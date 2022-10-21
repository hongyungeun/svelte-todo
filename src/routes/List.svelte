<script>
  import {onMount} from 'svelte'

  let isOk = false

  
</script>

<div class="list_wrap">
<p class="list_item" class:on={isOk}>
  <slot>asdasd</slot>
</p>
<input type="button" on:click={() => {isOk = !isOk}} value="확인">
<div>삭제</div>

</div>

<style>
.list_item {
  min-width: 100px;
}
.on {
  text-decoration: line-through;
}
</style>