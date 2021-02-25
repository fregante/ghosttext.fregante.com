---
layout: default
title: 👻 GhostText — Use your text editor in the browser
style: centered
footer: |
  Editor extensions developed by third parties! Original proof of concept by Guido Krömer. App logos belong to their respective owners. <br><a href="https://github.com/fregante/GhostText">Code</a> released under MIT license.
---

<img src="demo.gif" alt="GhostText demo screencast" width="458" height="515" />

Whenever you’re writing more than a little snippet of code anywhere on the web, activate GhostText to open your preferred text editor and enjoy your own development environment.

## Installation

GhostText is a browser extension that connects to your editor via its own extension. Install both extensions and, if necessary, start the GhostText server in the editor’s extension.

<h3 id="browser">Choose your browser</h3>

<ul class="apps">
	<li>
		<a target="_blank" href="https://chrome.google.com/webstore/detail/refined-github/godiecgffnchndlihlpaajjcplehddca">
			<img src="https://raw.githubusercontent.com/alrra/browser-logos/main/src/chrome/chrome_128x128.png" width="48" height="48" alt="Chrome" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/ghosttext/">
			<img src="https://raw.githubusercontent.com/alrra/browser-logos/main/src/firefox/firefox_128x128.png" width="48" height="48" alt="Firefox" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://apps.apple.com/app/ghosttext/id1552641506">
			<img src="https://raw.githubusercontent.com/alrra/browser-logos/main/src/safari/safari_128x128.png" width="48" height="48" alt="Safari" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://chrome.google.com/webstore/detail/refined-github/godiecgffnchndlihlpaajjcplehddca">
			<img src="https://raw.githubusercontent.com/alrra/browser-logos/main/src/edge/edge_128x128.png" width="48" height="48" alt="Edge" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://chrome.google.com/webstore/detail/refined-github/godiecgffnchndlihlpaajjcplehddca">
			<img src="https://raw.githubusercontent.com/alrra/browser-logos/main/src/opera/opera_128x128.png" width="48" height="48" alt="Opera" />
		</a>
	</li>
</ul>

<h3 id="editor">Choose your text editor</h3>

<ul class="apps">
	<li>
		<a target="_blank" href="https://sublime.wbond.net/packages/GhostText">
			<img src="/icons/sublime-text.svg" alt="Sublime Text" width="48" height="48" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://marketplace.visualstudio.com/items?itemName=tokoph.ghosttext">
			<img src="/icons/vscode.svg" alt="VS Code" width="48" height="48" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://github.com/GhostText/GhostText-for-Atom">
			<img src="/icons/atom.svg" alt="Atom" width="48" height="48" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://melpa.org/#/atomic-chrome">
			<img src="/icons/emacs.svg" alt="Emacs" width="48" height="48" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://github.com/raghur/vim-ghost">
			<img src="/icons/vim.svg" alt="Vim" width="48" height="48" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://github.com/subnut/nvim-ghost.nvim">
			<img src="/icons/neovim.svg" alt="Neovim" width="48" height="48" />
		</a>
	</li>
	<li>
		<a target="_blank" href="https://github.com/fhs/Ghost">
			<img src="/icons/acme.png" alt="Acme" width="48" height="48" />
		</a>
	</li>
</ul>

Most editor extensions are by third parties. You can create more extensions for your editor! Refer to the [protocol](https://github.com/fregante/GhostText/blob/main/PROTOCOL.md) file.

## Usage

Once you install both extensions, you can activate GhostText in the current browser tab by clicking its icon in the toolbar or by using a [keyboard shortcut](#keyboard-shortcuts). The editor will need to be already open.

Notice: in some editors you’ll need to run the _Enable GhostText_ command to start the server. Refer to the documentation of your editor’s GhostText extension. Sublime Text doesn’t need this step.

## How it works

GhostText is split in two parts:

1. a HTTP and WebSocket server in the text editor
2. a client in the browser

When you activate GhostText with a click, the browser will try contacting the server in the text editor (at the port specified in the options) and open a WebSocket connection. Every change will be transmitted to the other side. Each side can close the socket (for example by closing the window) and the session will be automatically over.

## Keyboard shortcuts

These are the default shortcuts, they can be [customized in Chrome](https://lifehacker.com/add-custom-keyboard-shortcuts-to-chrome-extensions-for-1595322121) and [Firefox](https://support.mozilla.org/en-US/kb/manage-extension-shortcuts-firefox), but not yet in Safari.

<table>
	<tr>
		<th>Windows</th>
		<td><kbd>ctrl</kbd> + <kbd>shift</kbd> + <kbd>K</kbd></td>
	</tr>
	<tr>
		<th>Linux</th>
		<td><kbd>ctrl</kbd> + <kbd>shift</kbd> + <kbd>H</kbd></td>
	</tr>
	<tr>
		<th>Mac</th>
		<td><kbd>cmd</kbd> + <kbd>shift</kbd> + <kbd>K</kbd></td>
	</tr>
</table>

## More

[GhostText on GitHub](https://github.com/fregante/GhostText) — [Troubleshooting](/troubleshooting/)
