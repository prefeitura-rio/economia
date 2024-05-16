<!-- src/components/Footer.svelte -->

<script>
  import logo from "$svg/logo.svg"; 
	// import { activeBar } from "$stores/misc.js";
</script>


 <footer class="footer">
	<div class="footer_logo">
		<img class="photo_logo" src="assets/img/intro/logo_preto_horizontal.png" alt="Foto" />
	</div>
	<br>
	<br>
 </footer>
 
 <style>
	@media (max-width: 640px) {
		.footer{
			margin-left: 0.9rem ;
		}
	}
	#autores, #agradecimentos, #prefeito{
		border-bottom: 3px solid var(--color-highlight);
		font-size: 25px;
	}
	.footer_logo{
		padding-top:10rem;
		padding-bottom:10rem;
	}
	.photo_logo{
		width: 200px;
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
 