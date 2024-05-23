<!-- src/components/Footer.svelte -->

<script>
  import logo from "$svg/logo.svg"; 
	// import { activeBar } from "$stores/misc.js";
</script>


 <footer class="footer">
	<div class="footer_logo">
		<img class="photo_logo" src="assets/img/intro/logo_preto_horizontal.png" alt="Foto" />
		<img class="photo_logo2" src="assets/img/intro/logo.png" alt="Foto" />
	</div>
	<br>
	<br>
 </footer>
 
 <style>
	@media (max-width: 640px) {
		.footer{
			margin-left: 0.9rem ;
		}
		.footer_logo{
			display: flex;
			flex-direction: column;
			align-items: center !important;
			gap: 3rem !important;
		}
		.photo_logo{
		width: 220px !important;
		height: auto !important;
		/* height: 53px; */
	}
	.photo_logo2{
		width: auto;
		height: 50px;
	}
	}
	#autores, #agradecimentos, #prefeito{
		border-bottom: 3px solid var(--color-highlight);
		font-size: 25px;
	}
	.footer_logo{
		display: flex;
		gap: 1rem;
		/* padding-top:-1rem; */
		/* padding-bottom:-1rem; */
	}
	.photo_logo{
		width: auto;
		height: 53px;
	}
	.photo_logo2{
		width: auto;
		height: 50px;
	}
	.footer {
	margin-bottom: 15vh;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 20px;

}
	.footer h3,
	.footer h6 {
		margin: 0 20px 10px;
		font-size: 15px;
	}
	
	.footer h3{
		font-weight: bold
	}
 

 </style>
 