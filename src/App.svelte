<script>
	
</script>

<style>
	
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