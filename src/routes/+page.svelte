<script>
  import {onMount} from 'svelte'
  import './style.css'
  import List from './List.svelte'
  
  
  let value;
  let id=3
  
  let text =''
  let propVal = [{
    id:1,
    value:'1번할일',
    
  },{
    id:2,
    value:'2번할일',
    
  }
]

  $: listLength= propVal.length;
  
  function todoPlus (){
    if(value == ''){
      alert('할일 입력하고 확인누르쇼')
    }else{
      propVal.push({
        id,
        value
      })
      propVal = propVal
      value=''
      id +=1
      
    }
  }

  console.log(listLength)
</script>

<div class="wrap">
  <div class="input_wrap">
    <p class="title">To Do List</p>
    <div class="write_input">
      <input bind:value={value} type="text" placeholder="할일">
      <button on:click={todoPlus}>확인</button>
    </div>
  </div>
  <div class="length_wrap">
    현재 남은 할일 갯수 : 
    {#if listLength}
      {listLength}
    {/if}
  </div>
  <div class="box">
    {#each propVal as item }
      <List propVal = {propVal} item={item}></List>
    {/each}
  </div>
</div>

<style>
  input {
    font-size: 16px;
    border: none;
    background: white;
    border-radius: 20px;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.299);
  }
  input:focus{
    outline: none;
  }
  .wrap {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    width: 500px;
    height: 500px;
  }
  .input_wrap {
    margin-bottom: 30px;
  }
  .title {
    font-size: 30px;
    font-weight: bold;
  }
  .write_input{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 10%;
    gap: 30px;
  }
  button {
    background: dodgerblue;
    padding: 10px;
    border-radius: 10px;
    border: none;
    width: 100px;
    font-weight: bold;
    font-size: 16px;
    color: white;
    cursor: pointer;
  }
  button:active {
    opacity: 0.7;
  }
  .input_wrap input{
    width: 80%;
    padding:  15px;

  }
</style>