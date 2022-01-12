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

{% include browsers.html %}

<h3 id="editor">Choose your text editor</h3>

{% include editors.html %}

Most editor extensions are authored by third parties. You can create more extensions for your favorite editor! Refer to [the protocol document](https://github.com/fregante/GhostText/blob/main/PROTOCOL.md).

## Usage

Once you have installed both browser and editor extensions, you can activate GhostText in the current browser tab by clicking its icon in the toolbar or by using a [keyboard shortcut](#keyboard-shortcuts). The editor needs to be launched first.

Notice: in some editors you’ll need to run the _Enable GhostText_ command to start the server. Refer to the documentation of each extension. Sublime Text doesn’t need this step.

## How it works

GhostText is split in two parts:

1. A HTTP and WebSocket server in the text editor
2. A client in the browser

When you activate GhostText, the browser will try contacting the server in the text editor (at the port specified in the options) and open a WebSocket connection. Every change will be transmitted to the other side. Each side can close the socket (for example by closing the window) and the session will be automatically over.

## Keyboard shortcuts

These are the default shortcuts, they can be customized in [Chrome](https://lifehacker.com/add-custom-keyboard-shortcuts-to-chrome-extensions-for-1595322121) and [Firefox](https://support.mozilla.org/kb/manage-extension-shortcuts-firefox), but not yet in Safari.

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
