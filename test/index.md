---
layout: default
title: Testing GhostText 👻
---

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.32.0/codemirror.min.css" />
<style>
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
<p class="text-align-center">If it doesn't work, try <a href="/troubleshooting/">Troubleshooting</a></p>

## `<textarea>`

<div class="flex">
	<textarea>This is a textarea</textarea>
	<textarea>This is a second textarea</textarea>
</div>

## `contenteditable`

<div contenteditable class="field">This is a <em>contenteditable</em> div</div>

## CodeMirror

<!-- prettier-ignore-start -->

<textarea id="codemirror-field" class="field">
This is a CodeMirror field




</textarea>

<!-- prettier-ignore-end -->

<script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.32.0/codemirror.min.js"></script>
<script>
	window.CodeMirror.fromTextArea(document.getElementById('codemirror-field'), {
		lineNumbers: true,
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

## Fields inside iframe

<iframe src="." frameborder="0" class="field">One level deep, please!</iframe>
