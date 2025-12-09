---
title: "Download"
tagline: "Get the latest and the greatest release here."
layout: single
classes: wide
permalink: /download/
latest_version: "25.11"
---

# Downloading the game

Please note that the asset files from *Chris Sawyer's Locomotion* are required for OpenLoco to work.
It can be bought on e.g. [Steam](https://store.steampowered.com/app/356430/) or [GOG.com](https://www.gog.com/game/chris_sawyers_locomotion).

The latest version of OpenLoco is v{{page.latest_version}}.<br>
[Changelog](https://github.com/OpenLoco/OpenLoco/releases/v{{page.latest_version}}/)<br>
[Release announcement](https://openloco.io/news/20{{page.latest_version | replace: ".", "/"}}/openloco-v{{page.latest_version}}.html)

<a class="btn btn--large btn--success" id="download-link"
	href="https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-Win32.zip">
	Download OpenLoco v{{page.latest_version}} for <span id="platform">Windows</span><br>
	<span id="platform-byline" style="font-size: 0.75rem; font-weight: normal">(.zip, 32-bits, Intel x86)</span>
</a>

<script type="text/javascript" defer>
	const kBaseReleaseUrl = 'https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-%PLATFORM%.%EXT%';

	const kPlatform = window.navigator.platform;
	const kMacOsPlatforms = ['macOS', 'Macintosh', 'MacIntel'];
	const kWindowsPlatforms = ['Win32', 'Win64', 'Windows'];

	// TODO: verify/expand the following before release
	const kSupportedPlatforms = {
		linux:   { 'url_keyword': 'linux', 'ext': 'deb', 'label': 'Debian',  'byline': '64-bits, Intel x86-64' },
		macos:   { 'url_keyword': 'macos', 'ext': 'zip', 'label': 'macOS',   'byline': '64-bits, Apple Silicon' },
		windows: { 'url_keyword': 'win64', 'ext': 'zip', 'label': 'Windows', 'byline': '64-bits, Intel x86-64' },
	};

	let platform = null, suggestedReleaseUrl = null;
	if (kMacOsPlatforms.indexOf(kPlatform) !== -1) {
		platform = kSupportedPlatforms['macos'];
	} else if (/Linux/.test(kPlatform)) {
		platform = kSupportedPlatforms['linux'];
	} else {
		platform = kSupportedPlatforms['windows'];
	}

	const kDownloadLink = document.getElementById('download-link');
	kDownloadLink.href = kBaseReleaseUrl.replace('%PLATFORM%', platform.url_keyword).replace('%EXT%', platform.ext);

	const kPlatformLabel = document.getElementById('platform');
	kPlatformLabel.textContent = platform.label;

	const kBylineLabel = document.getElementById('platform-byline');
	kBylineLabel.textContent = platform.byline;
</script>

Alternatively, IntelOrca's [OpenLauncher](https://github.com/IntelOrca/OpenLauncher) can be used
to automatically stay up-to-date with the latest OpenLoco release.


## For Windows

The latest release can be downloaded from GitHub using the links below.
For best performance, please use the 64-bit version if your OS supports it.

To install OpenLoco, extract the zip file found below to your preferred folder, e.g. `C:\Program Files\OpenLoco`.
We recommend putting OpenLoco in a *different* folder than the the original Locomotion files.

<a class="btn btn--success" id="download-link"
	href="https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-Win32.zip">
	Download OpenLoco v{{page.latest_version}} for Windows<br>
	<span style="font-size: 0.75rem; font-weight: normal">(.zip, 32-bits, Intel x86)</span>
</a>
<a class="btn btn--success" id="download-link"
	href="https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-Win64.zip">
	Download OpenLoco v{{page.latest_version}} for Windows<br>
	<span style="font-size: 0.75rem; font-weight: normal">(.zip, 64-bits, Intel x86-64)</span>
</a>


## For macOS

The latest release can be downloaded from GitHub using the links below.
We support Apple Silicon processors (M1 onwards).

To install OpenLoco, extract the zip file found below, and move `OpenLoco.app` to your preferred folder,
e.g.&nbsp;`/Applications`.
Currently, this app bundle is not signed. You may need to add a GateKeeper exception
in order to open it, e.g.:
```
$ xattr -d com.apple.quarantine OpenLoco.app
```

Please note that a copy of the original Locomotion files is required. We recommend putting these in
a different folder, e.g. somewhere in your user folder.

<a class="btn btn--success" id="download-link"
	href="https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-macos.zip">
	Download OpenLoco v{{page.latest_version}} for macOS<br>
	<span style="font-size: 0.75rem; font-weight: normal">(.zip, 64-bits, Apple Silicon)</span>
</a>


## For Linux/BSD

We currently provide release builds for Intel 64-bit builds of Ubuntu.
On other platforms, CMake may be used to compile builds for your platform.
Please refer to the [README file on GitHub](https://github.com/OpenLoco/OpenLoco#linux-1) for details.

Please note that a copy of the original Locomotion files is required. We recommend putting these in
a different folder, e.g. somewhere in your home directory.

<a class="btn btn--success" id="download-link"
	href="https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-ubuntu.deb">
	Download OpenLoco v{{page.latest_version}} for Ubuntu<br>
	<span style="font-size: 0.75rem; font-weight: normal">(.deb, 64-bits, Intel x86-64)</span>
</a>
