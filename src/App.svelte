<!--

<script>
	import { onMount } from 'svelte';
	let faqItems = [
    { question: "What is Frontend Mentor, and how will it help me?", answer: "Frontend Mentor offers realistic coding challenges to help developers improve their frontend coding skills with projects in HTML, CSS, and JavaScript. It's suitable for all levels and ideal for portfolio building.", isOpen: false },
    { question: "Is Frontend Mentor free?", answer: "Yes, Frontend Mentor offers both free and premium coding challenges, with the free option providing access to a range of projects suitable for all skill levels. ", isOpen: false },
    { question: "Can I use Frontend Mentor projects in my portfolio?", answer: "Yes, you can use projects completed on Frontend Mentor in your portfolio. It's an excellent way to showcase your skills to potential employers! ", isOpen: false },
	{ question: " How can I get help if I'm stuck on a Frontend Mentor challenge?", answer: "The best place to get help is inside Frontend Mentor's Discord community. There's a help channel where you can ask questions and seek support from other community members.", isOpen: false },
  ];
  
  let backgroundImage = '/background-pattern-desktop.svg';

  function toggleAnswer(index) {
    faqItems[index].isOpen = !faqItems[index].isOpen;
  }

   onMount(() => {
   
    if (window.innerWidth < 1080) {
      backgroundImage = '/background-pattern-mobile.svg';
    }
  });
</script>

<style>
	:root{
		--bg_color: hsl(275, 100%, 97%);
		--text-colorAns: hsl(292, 16%, 49%);
		--text-colorQ: hsl(292, 42%, 14%);
		--font:'Work Sans', sans-serif;
	}

	:global(body){
		padding: 0;
		margin: 0;
		background-color: var(--bg_color);
		font-family: var(--font);   	 
	}


	.main-container{
		
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%,-50%);
		background-color: hsl(0, 0%, 100%);
		padding: 20px;
		border-radius: 10px;
		width: 50%;
		box-shadow: 0 6px 6px rgba(0, 0, 0, 0.1);
		
	}

	button{
		background: none;
		border: none;
		cursor: pointer;
	}

	.faq-header{
		display: flex;
	}

	h1{
		margin: 0;
		padding: 0;
		font-size: 38px;
		
	}

	.alignment{
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.icon-style {
		padding-top: 25px;
	}

	.faq-container{
	
		padding-bottom: 10px;
		border-bottom: 1px solid rgb(169, 165, 165);
	}

	.faq-header img{
		width: 40px;
		height: 40px;
		padding-right: 10px;
	}

	.question-style{
		
		font-weight: bold;
		font-size: 16px;
		color: black;	
	}

	.question-style:hover{
		color: var(--text-colorAns);
		
	}

	.answer-style{
		color: var(--text-colorAns);
		font-size: 16px;
	}

	@media (min-width: 1080px){
		.main-container{
			width: 30%;
		}	

	}

	@media (max-width: 768px){
		h1{
			font-size: 29px;
		}
		.question-style{
			font-size: 13px;
		}
		.answer-style{
			font-size: 13px;
		}

		.icon-style {
		padding-top: 15px;
	}
	.main-container{
		width: 65%;
	}
	}
	
</style>

<body>
	
	<div style="background-image: url({backgroundImage});">
  		<img src={backgroundImage} alt="background_image"/>
	</div>

	<div class="main-container">
		<div class="faq-header">
			<img src = "/icon-star.svg" alt="faq-title"/>
			<h1>FAQs</h1>
		</div>

		<div>
			{#each faqItems as faqItem, index}
				<div class="faq-container" style="{index === faqItems.length - 1 ? 'border-bottom: none;' : ''}">
					<div>
						<div class="alignment">
							<div class="question-style">
								<span>{faqItem.question}</span>
							</div>
							<div >
								<button class="icon-style" on:click={() => toggleAnswer(index)}>
								{#if faqItem.isOpen}					
									<img src = "/icon-minus.svg" alt="minus icon"/>
								{:else}
									<img src = "/icon-plus.svg" alt="minus icon"/>
								{/if}
								</button>
							</div>
						</div>
					
						{#if faqItem.isOpen}
						<p class="answer-style">{faqItem.answer}</p>
						{/if}
					</div>
				</div>
			{/each}
		</div>
	</div>

</body> 
-->

<script>
  import FAQItem from './FAQItem.svelte';
  import { onMount } from 'svelte';

  let faqItems = [
    { question: "What is Frontend Mentor, and how will it help me?", answer: "Frontend Mentor offers realistic coding challenges to help developers improve their frontend coding skills with projects in HTML, CSS, and JavaScript. It's suitable for all levels and ideal for portfolio building.", isOpen: false },
    { question: "Is Frontend Mentor free?", answer: "Yes, Frontend Mentor offers both free and premium coding challenges, with the free option providing access to a range of projects suitable for all skill levels. ", isOpen: false },
    { question: "Can I use Frontend Mentor projects in my portfolio?", answer: "Yes, you can use projects completed on Frontend Mentor in your portfolio. It's an excellent way to showcase your skills to potential employers! ", isOpen: false },
    { question: " How can I get help if I'm stuck on a Frontend Mentor challenge?", answer: "The best place to get help is inside Frontend Mentor's Discord community. There's a help channel where you can ask questions and seek support from other community members.", isOpen: false },
  ];

  let backgroundImage = '/background-pattern-desktop.svg';

  function toggleAnswer(index) {
    faqItems[index].isOpen = !faqItems[index].isOpen;
  }

   onMount(() => {
   
    if (window.innerWidth < 1080) {
      backgroundImage = '/background-pattern-mobile.svg';
    }
  });


</script>

<style>

	:root{
		--bg_color: hsl(275, 100%, 97%);
		--text-colorAns: hsl(292, 16%, 49%);
		--text-colorQ: hsl(292, 42%, 14%);
		--font:'Work Sans', sans-serif;
	}

	:global(body){
		padding: 0;
		margin: 0;
		background-color: var(--bg_color);
		font-family: var(--font);   	 
	}

 
  .main-container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: hsl(0, 0%, 100%);
    padding: 25px;
    border-radius: 10px;
    width: 50%;
    box-shadow: 0 6px 6px rgba(0, 0, 0, 0.1);
  }

	.faq-container {
    padding-bottom: 10px;
    border-bottom: 1px solid rgb(169, 165, 165);
  }

  .faq-header {
    display: flex;
  }

  h1 {
    margin: 0;
    padding: 0;
	padding-left: 5px;
    font-size: 38px;
  }

               

  @media (min-width: 1080px) {
    .main-container {
      width: 30%;
    }
  }

  @media (max-width: 768px){
		h1{
			font-size: 33px;
		}	
	
	.main-container{
		width: 65%;
	}
	}

	
</style>

<div style="background-image: url({backgroundImage});">
  		<img src={backgroundImage} alt="background_image"/>
</div>

<div class="main-container">
  <div class="faq-header">
    <img src="/icon-star.svg" alt="faq-title"/>
    <h1>FAQs</h1>
  </div>

  {#each faqItems as faqItem, index}
  	<div class="faq-container" style="{index === faqItems.length - 1 ? 'border-bottom: none;' : ''}">
		<FAQItem question={faqItem.question} answer={faqItem.answer} isOpen={faqItem.isOpen}/>
	</div>
  {/each}

</div>



