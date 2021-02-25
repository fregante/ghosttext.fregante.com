---
layout: default
title: Troubleshooting GhostText 👻
---

## Troubleshooting

<p class="text-align-center">
	Is GhostText correctly configured? <br />
	Try activating it on this page, it should pick up this field:
</p>

<textarea rows="10">
function registerElements() {
	for (const element of document.querySelectorAll(selector)) {
		// TODO: Only handle areas that are visible
		//  && element.getBoundingClientRect().width > 20
		if (!knownElements.has(element)) {
			knownElements.set(element, new GhostTextField(element));
		}
	}
}
</textarea>

## Errors

<h3 id="no-supported-fields">No supported fields found</h3>

If you’re seeing this message, the page you’d like to use GhostText on doesn’t have any compatible fields:

- `<textarea>` elements
- [`contentEditable`](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_Editable) areas: like in Gmail
- [CodeMirror](https://codemirror.net/) editors: used on CodePen, JSFiddle, JS Bin, …
- [Ace](https://ace.c9.io/) editor: used on AWS, Khan Academy, Wikipedia, …

<h3 id="unable-to-connect">Unable to connect to the editor</h3>

If you’re seeing this message, the browser extension can’t find the GhostText server running in an editor. Ensure that:

- Your editor is open
- Its GhostText extension is installed; Install it from the [list of supported editors](/#installation) if you haven’t already.
- The GhostText server is running; In most editor extensions this is started automatically.
- The server port matches; It’s 4001 by default, it can be changed in the options.
- There are no other servers using the port. For example what happens when you open http://localhost:4001? The page should return details about WebSocket and the editor should start a new connection.

If it still doesn’t work, try again in [Sublime Text](https://www.sublimetext.com), it’s the main supported editor of GhostText.
