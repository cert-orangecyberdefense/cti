Emmenhtal is a malicious loader likely distributed since early 2024, and first publicly detailed by Orange Cyberdefense CERT in August 2024.
Emmenhtal is an obfuscated multistage payload that spawns an execution of the LOLBIN mshta.exe to read a first HTA stage that embeds a malicious JavaScript code. Once interpreted and executed, the JavaScript decodes and runs a PowerShell script. The latter decrypts an obfuscated PowerShell loader which finally downloads and runs final-stage stealers and commodity RATs.

As of March 2025, our CERT has been tracking three versions of the loader, all actively distributed.

Emmenhtal v1

Emmenhtal v1 was (and still is) mainly distributed through executables padded with a malicious HTA script which characterizes Emmenhtal's first stage. As previously detailed, most of these executables masquerade as legitimate Windows binaries, such as  appidtel.exe, sethc.exe, rmactivate.exe, SearchProtocolHost.exe, dialer.exe etc...

Over the months, Emmenhtal v1 was observed in multiple distribution clusters and delivering a large umbrella of commodity RATs and stealers (Lumma, CryptBot, Meduza RAT, Remcos RAT, XWorm, RedLine stealer), indicating the malware is likely used by several threat actors.

Emmenhtal v2

Emmenhtal v2 surfaced in early December 2024, with several new obfuscation features. Compared to its predecessor, the v2 was not well detected by AV solutions and this is still the case three months after the variant surfaced. 
The new variant is still multistage, but no longer relies on HTA data hidden in the padding of a PE executable. Instead, its first stage corresponds to a data file with HTA script tags splitted all over the file, and intertwined with junk script lines designed to complicate analysis. Stages 2 and 3 remained pretty similar to the original Emmenhtal version. Finally, the last Powershell stage was also modified with a monoalphabetic substitution obfuscation method. Our Reverse Engineering team also identified back in December new features designed to hide the execution of the malware (using windows hidden outside of the screen, or error message masking).

Emmenhtalv2 has been mainly distributed through fake CAPTCHAs and “ClickFix” contents. In most cases, Emmenhtal either masquerades as a data file or a mp4 video.

Emmenhtal v3

Emmenhtal v3 surfaced in early March 2025, with many changes added to the HTA, JS and last Powershell stages, including new mouse movements speed check.

Current infection chains seem to leverage either fake CAPTCHAs verification on a compromised or malicious website leading to .mp4 files, or trojanized .mp3 files masquerading as songs and likely downloaded from file sharing platform MediaFire.
Most of these chains includes a new intermediary stage (a Powershell with AMSI bypass feature which loads in memory a .NET stage) in charge of delivering stealers.


