<script>
	let inputData = '';

	let outputData = '';

	let inputHandler = () => {
		let result = '[\n';
		let lines = inputData.split('\n');

		for (let i = 0; i < lines.length; i++) {
			let line = lines[i].trim();
			if (line.length > 0) {
				result += '  "' + line + '"';
				if (i < lines.length - 1) {
					result += ',\n';
				}
			}
		}

		result += '\n]';

		outputData = result;
	};
</script>

<div class="main">
	<div class="inner">
		<h1>Input</h1>

		<textarea bind:value={inputData} rows="5" on:input={inputHandler} />
	</div>

	<div class="inner">
		<h1>Output</h1>

		<textarea bind:value={outputData} rows="5" />
	</div>
</div>

<style>
	* {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}
	div.main {
		display: flex;
		height: 100vh;
	}

	textarea {
		font-family: monospace;
		font-size: 1.2em;
		width: 100%;
		margin: 5px;
		height: 90%;
	}

	div.inner {
		padding: 16px;
		flex: 1;
		width: 100%;
		height: 100%;
	}

	h1 {
		text-align: center;
	}
</style>
