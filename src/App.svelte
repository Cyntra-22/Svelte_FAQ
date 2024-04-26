<script>
	let faqItems = [
    { question: "What is Frontend Mentor, and how will it help me?", answer: "Frontend Mentor offers realistic coding challenges to help developers improve their frontend coding skills with projects in HTML, CSS, and JavaScript. It's suitable for all levels and ideal for portfolio building.", isOpen: false },
    { question: "Is Frontend Mentor free?", answer: "Yes, Frontend Mentor offers both free and premium coding challenges, with the free option providing access to a range of projects suitable for all skill levels. ", isOpen: false },
    { question: "Can I use Frontend Mentor projects in my portfolio?", answer: "Yes, you can use projects completed on Frontend Mentor in your portfolio. It's an excellent way to showcase your skills to potential employers! ", isOpen: false },
	{ question: " How can I get help if I'm stuck on a Frontend Mentor challenge?", answer: "The best place to get help is inside Frontend Mentor's Discord community. There's a help channel where you can ask questions and seek support from other community members.", isOpen: false },
  ];
  const src = "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.wallpaperflare.com%2Fsearch%3Fwallpaper%3Dpurple%2Blandscape&psig=AOvVaw2j8HnSoQQYbpDXdW2cVUcV&ust=1714155944777000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCLjG-9P-3YUDFQAAAAAdAAAAABAE"

  function toggleAnswer(index) {
    faqItems[index].isOpen = !faqItems[index].isOpen;
  }
</script>

<style>
	:root{
		--bg_color: rgb(255, 239, 249)
	}

	:global(body){
		padding: 0;
		margin: 0;
		background-color: var(--bg_color);   	 
	}

	.image_background {
    	width: 100%;
		
    
}



	.main-container{
		
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%,-50%);
		background-color: rgb(225, 161, 208);
		padding: 20px;
		border-radius: 10px;
		width: 50%;
		
	}

	button{
		background: none;
		border: none;
	}

	.faq-header{
		display: flex;
	}
	h1{
		margin: 0;
		padding: 0;
	}

	.alignment{
		width: 100%;
		display: flex;
		justify-content: space-between;
	}

	.faq-container{
		margin-top: 25px;
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
		font-family:Georgia, 'Times New Roman', Times, serif;
		font-size: 15px;
	}

	@media (min-width: 1080px){
		.main-container{
			width: 30%;
		}
	}
</style>

<body>
	<div class="image_background">
		<img src="https://img.freepik.com/free-vector/matrix-style-binary-code-digital-falling-numbers-blue-background_1017-37387.jpg" alt=""/>
	</div>

	<div class="main-container">
		<div class="faq-header">
			<img src = "images/logo.png" alt="faq-title"/>
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
							<div>
								<button on:click={() => toggleAnswer(index)}>
								{#if faqItem.isOpen}					
									<span>➖</span>
								{:else}
									<span>➕</span>
								{/if}
								</button>
							</div>
						</div>
					
						{#if faqItem.isOpen}
						<p>{faqItem.answer}</p>
						{/if}
					</div>
				</div>
			{/each}
		</div>
	</div>

</body>