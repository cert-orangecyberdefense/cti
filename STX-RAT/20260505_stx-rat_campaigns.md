🧵 Since March 2026, Orange Cyberdefense has been tracking a malware delivery cluster linking a fake FileZilla campaign with other software-themed lures, including LibreOffice and Google Drive Setup, as well as a ClickFix-based one.
Our investigation identified overlaps across these campaigns, and related samples were later publicly identified as STX RAT. 

#CTI #ThreatIntel #STXRAT

![Campaigns delivering STX RAT](https://world-watch-images.s3.gra.io.cloud.ovh.net/2026/05/stx_watermarked_compressed.png)

1/ Our investigation started from the publicly documented FileZilla campaign, which used a fake FileZilla website to distribute trojanized FileZilla 3.69.5 packages.
The campaign used two delivery variants:
a portable archive containing the legitimate FileZilla package plus a malicious version.dll
a single EXE installer dropping the same DLL during installation
In both cases, filezilla.exe sideloaded the DLL and triggered a staged infection chain that ultimately delivered a RAT.

2/ We identified overlaps with:
a malvertising chain using VBS lures impersonating Google Drive or LibreOffice
a ClickFix lure reported by a private source
These branches were supported by shared infrastructure and staging patterns.

3/ Key overlap points included infrastructure involving supp0v3[.]com, cdn0v3[.]com, and 147.45.178[.]61, multiple pages[.]dev staging hosts, and similar callback / tracking logic observed across the linked chains.

4/ In the FileZilla branch, the sideloaded loader performed anti-analysis and anti-virtualization checks, resolved C2 via DNS-over-HTTPS, and used callback logic with tracking parameters.
In the overlapping script-based activity we tracked, VBS / PowerShell stages and TAR-delivered components (1.bin and 2.txt) led to in-memory payload execution.

5/ Separately, eSentire later described a related script-based branch involving VBScript → JScript → TAR (1.bin + 2.txt) → PowerShell, which is consistent with the broader staging logic we observed across the cluster.
At the malware level, STX RAT is a Windows RAT with infostealer and HVNC capabilities. It uses a custom multi-stage unpacking chain, communicates over a proprietary TCP-based protocol with both clearweb and Tor fallback, and exposes broad post-exploitation functionality.
Notably, credential theft is only activated after successful C2 interaction.

6/ Bottom line: different lures, similar staging, same malware outcome.

7/ We published a full advisory for our customers on the infection chain, overlaps, and malware analysis. Related IoCs are also available in this public GitHub repository.
 

 
