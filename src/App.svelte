<script>
	import Player  from "./Player.svelte";
	let redScore = 20;
	let blueScore = 20;
	$: blueWon = redScore <= 0;
	$: redWon = blueScore <= 0;
	$: gameOver = blueWon || redWon;


</script>

<main>
	<h1>Magic The Gathering Counter</h1>
	<div id="container-controler">
		<Player 
		{gameOver}
		fontColor = "#0000AA"
		winningText = "Blue Wins" 
		score={blueScore}
		won = {blueWon}
		/>
		<Player 
		{gameOver}
		fontColor = "#AA0000"
		winningText = "Red Wins" 
		score={redScore}
		won = {redWon}
		/>
	</div>
	<button>Start Game</button>
</main>

<style>
	main {
		width:80% ;
		padding: 20px;
		border: solid gray 1px;
		margin: 0 auto ;
		background-color: wheat ;
		margin: 10vh auto;
	}

	#container-controler{
		display: flex;
	}

	button{
		display: block;
		width: 100%;
		margin-top: 20px;
		border: solid salmon 1px;
		background-color: sandybrown;
		color: rbg(61, 56, 56);
		font-size: 20px;
		border-radius: 3px;
	}
</style>