---
layout: default
title: Testing GhostText 👻
---

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.32.0/codemirror.min.css" />
<style>
	#monaco-field,
	.CodeMirror {
		height: 120px;
	}
	.flex {
		display: flex;
		justify-content: space-between;
	}
	.flex textarea {
		width: 49%;
	}
	iframe {
		opacity: 0.8;
		height: 300px;
		max-width: 80% !important;
	}
</style>

## Testing page

<p class="text-align-center">
	Is GhostText correctly configured? Try activating it on this page. It can pick up multiple fields at once, just activate it multiple times.
</p>
<p class="text-align-center">If it doesn't work, refer to <a href="/troubleshooting/">Troubleshooting</a>.</p>

## `<textarea>`

<div class="flex">
	<textarea>This is a textarea</textarea>
	<textarea>This is a second textarea</textarea>
</div>

## `contenteditable`

<div contenteditable class="field">This is a <em>contenteditable</em> div</div>

## CodeMirror 6

<div id="codemirror-6-field" class="field"></div>

<script type="importmap">
	{
		"imports": {
			"codemirror/": "https://deno.land/x/codemirror_esm@v6.0.1/esm/"
		}
	}
</script>
<script async type="module">
	import { basicSetup, EditorView } from "https://deno.land/x/codemirror_esm@v6.0.1/esm/codemirror/dist/index.js"

	new EditorView({
		doc: "This is a CodeMirror 6 field\n\n\n\n\n\n",
		extensions: [basicSetup],
		parent: document.querySelector('#codemirror-6-field'),
	})
</script>

## CodeMirror 5

<!-- prettier-ignore-start -->

<textarea id="codemirror-field" class="field">
This is a CodeMirror 5 field




</textarea>

<!-- prettier-ignore-end -->

<script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.32.0/codemirror.min.js"></script>
<script>
	const cm = window.CodeMirror.fromTextArea(document.getElementById('codemirror-field'), {
		lineNumbers: true,
		gutters: ['CodeMirror-linenumbers'],
	});
	cm.on('gutterClick', (cm, line) => {
		const info = cm.getLineHandle(line);
		if (info.widgets) {
			info.widgets.map(w => {
				const node = w.node;
				w.clear();
				node.parentNode.removeChild(node);
			});
		} else {
			const msg = document.createElement('textarea');
			msg.select();
			msg.setRangeText('This is a textarea as CodeMirror line widget');
			cm.addLineWidget(line, msg, {coverGutter: false, noHScroll: true});
		}
	});
</script>

## Ace

<pre id="ace-field" class="field">
This is a Ace field




</pre>

<script src="https://cdnjs.cloudflare.com/ajax/libs/ace/1.2.9/ace.js"></script>
<script>
	window.ace.edit('ace-field').setOption('maxLines', 30);
</script>

## Monaco

<div id="monaco-field" class="field"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/monaco-editor/0.34.1/min/vs/loader.js"></script>
<script>
	require.config({paths: {vs: 'https://cdnjs.cloudflare.com/ajax/libs/monaco-editor/0.34.1/min/vs'}});
	require(["vs/editor/editor.main"], function () {
		window.monaco.editor.create(
			document.getElementById('monaco-field'),
			{value: 'This is a Monaco field\n\n\n\n\n'},
		);
	});
</script>

## Fields inside iframe

<iframe src="." frameborder="0" class="field">One level deep, please!</iframe>
