<script>
  import {onMount} from 'svelte'
  import Page from './+page.svelte'
  export let propVal
  export let item;
  let isOk = false
  console.log(item)
  console.log(propVal)
  function deleteTodo(){
    propVal = propVal.filter(t =>{console.log(t.id !== item.id)
       t.id !== item.id})
    this.parentNode.remove()
    console.log(this.id)
  }
</script>

<div class="list_wrap">
  <input type="checkbox" on:click={()=>isOk = !isOk}>
  <p class="list_item" class:on={isOk}>
    {item.value}
  </p>
  
  
  <!-- <input type="button" on:click={() => {isOk = !isOk}} value="확인"> -->
<div on:click={deleteTodo}>삭제</div>

</div>

<style>
.list_item {
  min-width: 100px;
  width: 80%;
}
.list_wrap {
  display: flex;
  align-self: center;
  justify-content: space-between;
  width: 100%;
}
.on {
  text-decoration: line-through;
}
</style>