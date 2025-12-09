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


## Windows users

The latest release can be downloaded from GitHub using the link below.
Simply unzip the download to your preferred folder, e.g. `C:\Program Files\OpenLoco`.
We recommend putting OpenLoco in a *different* folder than the the original Locomotion files.

<a class="btn btn--large btn--success" id="download-link"
	href="https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-Win32.zip">
	Download OpenLoco v{{page.latest_version}} for <span id="platform">Windows</span><br>
	<span id="platform-byline" style="font-size: 0.75rem; font-weight: normal">(.zip, 32-bits, Intel x86)</span>
</a>

<script type="text/javascript" defer>
	const kBaseReleaseUrl = 'https://github.com/OpenLoco/OpenLoco/releases/download/v{{page.latest_version}}/OpenLoco-v{{page.latest_version}}-%PLATFORM%.zip';

	const kPlatform = window.navigator.platform;
	const kMacOsPlatforms = ['macOS', 'Macintosh', 'MacIntel'];
	const kWindowsPlatforms = ['Win32', 'Win64', 'Windows'];

	// TODO: verify/expand the following before release
	const kSupportedPlatforms = {
		linux:   { 'url_keyword': 'linux', 'label': 'Debian',  'byline': '64-bits, Intel x86-64' },
		macos:   { 'url_keyword': 'macos', 'label': 'macOS',   'byline': '64-bits, Apple Silicon' },
		windows: { 'url_keyword': 'win64', 'label': 'Windows', 'byline': '64-bits, Intel x86-64' },
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
	kDownloadLink.href = kBaseReleaseUrl.replace('%PLATFORM%', platform.url_keyword);

	const kPlatformLabel = document.getElementById('platform');
	kPlatformLabel.textContent = platform.label;

	const kBylineLabel = document.getElementById('platform-byline');
	kBylineLabel.textContent = platform.byline;
</script>

Alternatively, IntelOrca's [OpenLauncher](https://github.com/IntelOrca/OpenLauncher) can be used
to automatically stay up-to-date with the latest OpenLoco release.


## macOS users

As we are still working on reimplementing *Locomotion* in C++, we can only provide 32-bits builds.
For this reason, we cannot provide native builds for macOS. However, the game can be run at full performance
[using Wine](https://github.com/OpenLoco/OpenLoco/wiki/Running-OpenLoco-on-macOS) to run the Windows releases.
Wine taps into [Rosetta](https://support.apple.com/en-us/HT211861), which takes care of translating our Intel builds to Apple Silicon as well.

## Linux and BSD

For Linux and BSD distributions, we currently do not provide any builds. CMake may be used to compile builds for your platform. Please refer to the [README file on GitHub](https://github.com/OpenLoco/OpenLoco#linux-1) for details.
