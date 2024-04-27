<script>
  export let question;
  export let answer;
  export let isOpen;

  function toggleAnswer() {
    isOpen = !isOpen;
  }
</script>

<style>
  


  button {
    background: none;
    border: none;
    cursor: pointer;
  }

  .alignment {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .question-style {
    font-weight: bold;
    font-size: 16px;
    color: black;
  }

  .question-style:hover {
    color: var(--text-colorAns);
  }

  .answer-style {
    color: var(--text-colorAns);
    font-size: 16px;
  }
</style>


  <div class="alignment">
    <div class="question-style" >
      <span>{question}</span>
    </div>
    <div>
      <button class="icon-style" on:click={toggleAnswer}>
        {#if isOpen}
          <img src="/icon-minus.svg" alt="minus icon"/>
        {:else}
          <img src="/icon-plus.svg" alt="plus icon"/>
        {/if}
      </button>
    </div>
  
  {#if isOpen}
    <p class="answer-style">{answer}</p>
  {/if}
</div>
