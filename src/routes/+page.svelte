<script>
  import './style.css'
  import List from './List.svelte'
  let value;
</script>

<div class="wrap">
  <div class="input_wrap">
    <input bind:value={value} type="text">
    <button>확인</button>
  </div>
  <div class="box">
    <List></List>
  </div>
</div>

<style>
  input {
    font-size: 16px;
    border: none;
    border-bottom: 1px solid #000;
    background: none;
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
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 10%;
    gap: 30px;
  }
  button {
    background: dodgerblue;
    padding: 10px;
    border-radius: 10px;
    border: none;
    width: 100px;
  }
  .input_wrap input{
    width: 70%;
    padding: 5px 10px;
  }
</style>