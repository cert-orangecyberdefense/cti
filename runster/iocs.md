
# Runster — Indicators of Compromise

**TLP:WHITE** | Orange Cyberdefense

---

## URL patterns

```
# Payload A — delivery and C2
/run/[A-Za-z0-9]{8}
/take/[A-Za-z0-9]{8}(?:/<victim-id>)?
/process/[A-Za-z0-9]{8}(?:/<victim-id>)?
/validate/[A-Za-z0-9]{8}(?:/<victim-id>)?

# Payload B — delivery and C2
/gate/start/[A-Za-z0-9]{8}
/gate/init/[A-Za-z0-9]{8}(?:/<victim-id>)?
/gate/auto/[A-Za-z0-9]{8}(?:/<victim-id>)?

# Payload C — native EXE/DGA loader
/api/client_hello
/api/client/verify
/api/client/new
/tasks/get_worker
/tasks/collect
/avast_update
```

### Observed C2 URLs

```
# Payload A
hxxps://emeditorgb[.]com/run/mg8heP0r
hxxps://metrics[.]msft17[.]com/run/XYaR5gFi
hxxps://api[.]bio9438[.]com/run/dIG1bXo3
hxxps://events[.]msft23[.]com/run/dIG1bXo3
hxxps://orangewater00[.]com/run/mMbcjy2q
hxxps://events[.]msft23[.]com/take/dIG1bXo3/<UUID>
hxxps://events[.]msft23[.]com/process
hxxps://events[.]msft23[.]com/validate
hxxps://event[.]dis4cle[.]info/process/dIG1bXo3/<MachineGuid>
hxxps://event[.]dis4cle[.]info/take/dIG1bXo3/<MachineGuid>
hxxps://8mrzhrdm0obptpp[.]com/take/hAUjZrJo/<UUID>
hxxps://4kkaxgfdw7l1yvv4t9v[.]com/take/XstQk8Ja/<UUID>
hxxps://795n5qr4vk02wibh[.]com/take/WWboshwF/<UUID>
hxxps://event[.]dis4cle[.]info/1

# Payload B
hxxps://nc7d8p7u8j3n4hgm[.]com/gate/start/efeb550a
hxxps://keyactivate[.]cc/gate/start/e805d522
hxxps://emeditorde[.]com/gate/start/2daef8cd
hxxps://cachingdrive[.]com/gate/init/2daef8cd
hxxps://olive3451[.]com/gate/start/f8c45bba
hxxps://reshow35[.]com/gate/start/f8c45bba
hxxps://mo2307[.]com/gate/start/550bb89b
hxxps://mt7263[.]com/gate/start/c09d19a0
hxxps://mt7263[.]com/gate/init/c09d19a0/<victim-id>
hxxps://mt7263[.]com/gate/auto/c09d19a0/<victim-id>
hxxps://olive3451[.]com/gate/auto/f8c45bba/<UUID>

# Payload C — native EXE/DGA loader (sandbox-confirmed active domain)
hxxps://gmuikyswmaosaqwk[.]xyz/api/client_hello
hxxps://gmuikyswmaosaqwk[.]xyz/avast_update
hxxps://gmuikyswmaosaqwk[.]xyz/api/client/new
hxxps://gmuikyswmaosaqwk[.]xyz/tasks/get_worker
hxxps://gmuikyswmaosaqwk[.]xyz/tasks/collect
```

---

## Domains

### Lure / initial access

```
# Claude Code
claudecode[.]co[.]com
claude-code[.]co[.]com
claudecode-install[.]co[.]com
claude-setup[.]com
install-claude[.]com
setup-code[.]com

# Gemini CLI
geminicli[.]co[.]com
gemini-setup[.]com
use-gemini[.]com
gemini-cli[.]co[.]com

# Codex CLI
codexcli[.]co[.]com
codexcli[.]gr[.]com

# Chocolatey
chocolatey[.]co[.]com
chocolatey[.]net
chocolatey-setup[.]co[.]com
chocolatey-download[.]co[.]com

# KeePassXC
keepassxc[.]us[.]org
keepassxc[.]us[.]com

# Mullvad VPN
mullvad-vpn[.]us[.]org
mullvad-download[.]org
mullvad-download[.]it[.]com

# WinSCP
winscp-download[.]us[.]org
winscp-setup[.]net
winscp-app[.]org
winscp-downloads[.]com
winscp-ftps[.]com

# PuTTY
putty-setup[.]us[.]com

# Cyberduck
cyberduck[.]info
cyber-duck[.]co[.]com
cyberduck-ftp[.]com
cyberduck-download[.]org

# FileZilla
filezilla-project[.]us[.]com

# Joplin
joplin-download[.]com
joplin-desktop[.]app

# Amazon S3 Browser
s3-browser[.]quest
s3-browser-download[.]blog

# Monero
getmonero[.]us[.]com
get-monero[.]co[.]uk

# Node.js
nodejs-setup[.]co[.]com

# EmEditor lookalike pages (Dec 2025 supply-chain)
emeditorjp[.]com
emeditorjapan[.]com
emedorg[.]com
em-editor[.]co[.]com
emeditor-download[.]co[.]com
emurasoftwares[.]com
emeditorsb[.]com

# Other
openclow[.]co[.]com
```

### Payload A — delivery and C2

```
emeditorgb[.]com              token: mg8heP0r
emeditorltd[.]com             token: (EmEditor wave 2)
metrics[.]msft17[.]com        token: XYaR5gFi
8mrzhrdm0obptpp[.]com         token: hAUjZrJo
4kkaxgfdw7l1yvv4t9v[.]com    token: XstQk8Ja
795n5qr4vk02wibh[.]com        token: WWboshwF
orangewater00[.]com            token: mMbcjy2q
events[.]msft23[.]com         token: dIG1bXo3
events[.]ms709[.]com          token: dIG1bXo3
api[.]bio9438[.]com           token: dIG1bXo3
event[.]dis4cle[.]info        token: dIG1bXo3
celsius[.]proper829[.]com
proper829[.]com
```

### Payload B — delivery and C2

```
nc7d8p7u8j3n4hgm[.]com       token: efeb550a
keyactivate[.]cc               token: e805d522
n8n[.]kraski-event[.]ru       token: e805d522
emeditorde[.]com               token: 2daef8cd
emedjp[.]com
cachingdrive[.]com             token: 2daef8cd  (also browser extension C2 in EmEditor chain)
olive3451[.]com                token: f8c45bba
reshow35[.]com                 token: f8c45bba
mo2307[.]com                   token: 550bb89b
mt7263[.]com                   token: c09d19a0
kafeprog7[.]com                token: eed8b732
t4whkbae7kudrs6e91p4[.]website
wsx5bq7x90jdp0nkaclt[.]info
minecent[.]ru
```

### Browser extension C2

Primary:

```
cachingdrive[.]com
```

DGA fallback — generated for week of 2025-12-25 (seed changes weekly):

```
08qodmaloshm5zrwhww[.]xyz      sinkholed
0xax86xdizce7kg9cpdk[.]online  sinkholed
1a298k7iqspq52l4r9e[.]space    sinkholed
8mfi71rtud8fov5[.]org          sinkholed
973jgnzjgnwupd1nu[.]space      sinkholed
afdwtyy38efzk[.]app            unregistered
brt461jnbjvm52mw[.]biz         sinkholed
daj54smzpklt5kjq[.]space       sinkholed
gs9uuz4h0510qhob[.]io          unregistered
z2ctmmm61dm0c3wfic[.]store     unregistered
```

### Payload C — char-based DGA

Seed: 0xD01B (53275) · Format: `[a-z]{16}.xyz` · Validation: `GET /api/client_hello`

```
aaumkaikuiskmkoq[.]xyz        agamyguoaguqcqwo[.]xyz        agoescgauiiqkows[.]xyz
agqeiuackgcqeykc[.]xyz        amyggcquguyyeiiq[.]xyz        ceagcumeseayguos[.]xyz
cqcgceukucukqgcc[.]xyz        cqqeusagmsumsaqu[.]xyz        cwcwwwouwoquwgyq[.]xyz
cwoiycssoemoucie[.]xyz        eaesaomuougaqyia[.]xyz        eiauewaikweeycia[.]xyz
geekiucomeikwkwe[.]xyz        geqskwkqiewgemso[.]xyz        gmuikyswmaosaqwk[.]xyz
iciuiuwsuycewcoq[.]xyz        iwwkmoiggoqysoww[.]xyz        kgqeeaisoaiqgqge[.]xyz
meuqaskwuegugaki[.]xyz        mewcooquugmseqac[.]xyz        mkomyiwsacausoco[.]xyz
mkuaommsqukwiocg[.]xyz        oosyoewqyigwmuuk[.]xyz        oueyaogawqskioam[.]xyz
qskyqyuusogaoyqq[.]xyz        qsqiiwmaekysmyeq[.]xyz        qygamscksaeemwky[.]xyz
scysmqyiwkkqyswg[.]xyz        sqicseukemqymuee[.]xyz        swseymccoqqumgcu[.]xyz
uakgcesmkomuggsq[.]xyz        ugoyyoqaqmcgwoic[.]xyz        uoqgiqqcsgoiayya[.]xyz
uosakmqkuigkkygs[.]xyz        uumcceymkuymmqou[.]xyz        uuiyoogwsyiummeu[.]xyz
wkqqyymuqssmcwck[.]xyz        wsawwqukqoswswia[.]xyz        wsiaumaqgcqmsaiu[.]xyz
wsokigmuecgykwkg[.]xyz        wswsaekmkgicucoy[.]xyz        wsywucwsgkcocaik[.]xyz
wyaawkcwsqooqyia[.]xyz        wyuswuoyicqaqcgo[.]xyz        ycwkmaiggomgmqws[.]xyz
ycykoeesyqoauqks[.]xyz        yoeuemsuayskkoco[.]xyz        yoisccqsiaassaeq[.]xyz
yoouoqeewgceymki[.]xyz        ywciouwgweywuika[.]xyz        ywyimiyquqcakqos[.]xyz
```

### Payload C — wordlist-based DGA

Seed: 0x2507E (151678) · Format: `word1[-]word2[-]word3.xyz` · PRNG: xorshift32 · Up to 10,000 candidates
Note: associated with secondary PE samples

```
and-last-lock[.]xyz      andtangtick[.]xyz        anus-staylard[.]xyz      babyglee-all[.]xyz
bandrice-pity[.]xyz      bark-gruffhuge[.]xyz     biketype-not[.]xyz       born-dataaid[.]xyz
burp-flung-pilot[.]xyz   card-votecrew[.]xyz      char-avid-verb[.]xyz     clap-lawn-farm[.]xyz
cropriftmore[.]xyz       dealflung-four[.]xyz     deftmean-real[.]xyz      dice-grate-plan[.]xyz
died-halo-tang[.]xyz     dill-aidwork[.]xyz       disk-bask-rusk[.]xyz     dovepact-gist[.]xyz
drug-arereef[.]xyz       duck-fondmoan[.]xyz      duel-gulp-luck[.]xyz     dusk-omit-epic[.]xyz
earltoll-snap[.]xyz      fold-hide-deft[.]xyz     forkmoathale[.]xyz       fourhomethen[.]xyz
gain-daze-kept[.]xyz     getrichcurl[.]xyz        give-pore-upon[.]xyz     gladloanwhat[.]xyz
glow-died-fail[.]xyz     glow-once-four[.]xyz     goal-soil-see[.]xyz      grid-brisk-lard[.]xyz
gridgrimmorn[.]xyz       groan-brim-peak[.]xyz    hand-rave-sail[.]xyz     haul-mess-deny[.]xyz
heal-jazz-shop[.]xyz     healshot-have[.]xyz      her-vein-pool[.]xyz      hole-tilt-brim[.]xyz
hullmall-cool[.]xyz      huskrug-cold[.]xyz       iconropeknob[.]xyz       idea-nickdoor[.]xyz
idle-cocaspin[.]xyz      kiltwent-our[.]xyz       king-culmdown[.]xyz      knew-sillseem[.]xyz
lath-too-reap[.]xyz      lathvetoiris[.]xyz       leansold-vein[.]xyz      leersuregear[.]xyz
loansome-rare[.]xyz      matelame-door[.]xyz      mate-limegive[.]xyz      math-buoy-seen[.]xyz
modetallbeam[.]xyz       mothwellkeep[.]xyz       move-dram-film[.]xyz     nice-poolback[.]xyz
obeyyellwool[.]xyz       open-teem-test[.]xyz     page-vest-lost[.]xyz     partuserkeen[.]xyz
past-reefprin[.]xyz      pestrear-lamp[.]xyz      pogo-hunt-brisk[.]xyz    propgrab-bird[.]xyz
rank-idea-mass[.]xyz     riftfacetill[.]xyz       rollgropeamid[.]xyz      rosecodeknew[.]xyz
rule-bead-dust[.]xyz     said-site-luck[.]xyz     seemeet-vine[.]xyz       sill-flog-aunt[.]xyz
sing-hikemalt[.]xyz      slewportarcs[.]xyz       slimsidehero[.]xyz       song-pecktrim[.]xyz
spot-mask-cape[.]xyz     swaycladstop[.]xyz       tang-sail-and[.]xyz      tendnone-heel[.]xyz
the-dopevoid[.]xyz       this-maimreef[.]xyz      torn-midgegrim[.]xyz     true-gategrin[.]xyz
tuck-hoaxwade[.]xyz      turniron-mound[.]xyz     ugly-oursold[.]xyz       uglyshop-mare[.]xyz
ventbuckpull[.]xyz       wade-vinepeer[.]xyz      wind-cragblur[.]xyz      zone-pour-too[.]xyz
```

---

## IP addresses

| IP | Associated domains | Note |
| --- | --- | --- |
| `5.101.82[.]118` | emeditorjp · emeditorjapan · emedorg | EmEditor cluster |
| `5.101.82[.]159` | emeditorgb · emeditorltd · emurasoftwares | EmEditor cluster |
| `46.28.70[.]245` | emeditorde · emedjp | EmEditor cluster |
| `147.45.50[.]54` | cachingdrive | Extension C2 |
| `64.188.83[.]146` | keyactivate · n8n.kraski-event | — |
| `185.82.218[.]112` | nc7d8p7u8j3n4hgm | Earliest Payload B |
| `89.169.15[.]2` | 8mrzhrdm0obptpp | — |
| `93.152.217[.]77` | 4kkaxgfdw7l1yvv4t9v | — |
| `79.132.130[.]62` / `81.90.29[.]48` | 795n5qr4vk02wibh | — |
| `93.152.217[.]97` | events.ms709 · metrics.msft17 | — |
| `185.178.231[.]112` | orangewater00 | — |
| `138.124.67[.]183` | emurasoftwares | — |
| `45.150.66[.]3` | api.bio9438 · event.dis4cle.info · celsius.proper829 · uumcceymkuymmqou.xyz | Convergence node — PS A routes and native loader routes |
| `194.147.34[.]224` | reshow35 · kafeprog7 | — |
| `146.185.233[.]59` | mo2307 · olive3451 | — |
| `109.107.170[.]111` | Claude/Chocolatey/KeePassXC lure pages | MIRhosting Netherlands (BPH) |
| `5.8.18[.]129` | WinSCP/Mullvad/EmEditor lure pages | — |
| `5.8.18[.]88` | Gemini CLI lure pages | — |
| `34.139.245[.]0` | amyggcquguyyeiiq[.]xyz | — |

---

## File hashes

### Trojanised and fake installer MSIs

```
# EmEditor — WALSHAM INVESTMENTS LIMITED
# Microsoft ID Verified CS EOC CA 02 · validity Dec 21–24, 2025
4bea333d3d2f2a32018cd6afe742c3b25bfcc6bfe8963179dad3940305b13c98

# EmEditor — WALSHAM INVESTMENTS LIMITED
# Microsoft ID Verified CS EOC CA 01 · validity Dec 20–23, 2025
3d1763b037e66bbde222125a21b23fc24abd76ebab40589748ac69e2f37c27fc

# EmEditor — emeditorltd.com · Dec 29, 2025
ad84f28e9bb0fcaf30846b2563a353b649ab6dc85b36d4bf58ee61a2a95b740a

# EmEditor v25.4.4 — emeditorltd.com · Dec 31, 2025
da59acc764bbd6b576bef6b1b9038f592ad4df0eed894b0fbd3931f733622a1a

# EmEditor (SHA1)
e5678fd66ac09205f55dc4fae9601185a76b2f50
ff78a86746bdcc6ed1390ff291a6c599e96e8487
826af8619430e7363e9eb3b2395b36cf6365b7bd
81e1ccbd3b4ed5a7593cfba21315c65ad4635f73

# Fake Mullvad VPN — Xiamen Quanlian (Sectigo)
a4b6e81233ca2b8a4c6ace3da6344a7e0a8df92ee06c4763c7b18001c169b133

# Fake KeePassXC — Shenzhen Xingzhongxing (Sectigo)
fa68320fd6c7ea9849145066b7b13507cf4186900a218cdc67d387341632d825
b4ad76f7fab47d36f538df5f8f7b5d5f41f15a6c2c3a9c128dd1d49b3d96957c
```

MSI embedded CustomAction scripts:

```
bcfda6fca68dfa203de0db0624b73a9ac22592eae708c12f17d4fff8ec99e9fc
a04727075910c90456043985e9d5119342adc77f1b45e76a7e1a79f92c1facd6
7ec4ec4511404553934e0bf08f3f124544f9a76857089feb96277ddad4f15592
```

### First-stage scripts

```
# EmEditor orchestrator — fetches both Payload A and B (RunspacePool)
660fdf42c9c32a68fc36dfd8b009dfc57f9424c6a77e8525fab044bbf419829b
0727237bb0aee8ac452eeeb2250cf9760ed78a67115c6466b8c4414e3d89a1c7

# EmEditor first-stage downloader (SHA1)
a3ab5e58a9330dd673dec17777e5110bf3c9eba3

# ClickFix lure scripts
5071921cb1ca369fe8f7af522a00373c8c85e4357f7ea1879d2cb4ae791797d6
80ffc86673bd8c8bd5862bbe961323a822b23c94df48c685162c571445552faa
b7f71a5a2df2aa38c1a4229cb16df0a123eb73923e6e0699c2a177f9e2e63d88

# Stage redirectors and loaders
ae8f70dad97fedecd707977ca22fd6f656c64c0dac96e03f0f4a6c04d0693f59
aeb622aadf8cba10da94773346cfa65eff76a4ad958dd9e2ef6c3109f95e4d28
1439d30ebeac3a6ccb9545acaa350783a83cc08746cb575e59ddb0efc77d412a
2d9ecc9321994558d0cc0e9d3fa9fdf600bacfe8758976d34f26f89c33bd5007
ae9bc11adb457930d402844bd3bf3af8ea7c13fdb7ea269fbe73877b18af1ca8
c213ce07b5791abd334ff749b5f05ecc6b40772d35ef4388b5f576bc3e619765
efbf87447d93f4232b1169920f75c2066d19863ebc28fb2d2662353dc4ef61d8
b9702ecf2928354dfc32e25468848408de40b82d237f83953fdc6d6d655050ef
```

### Payload A — credential theft

```
986399b6ddcfe718a174fa614a1f351079d64398194f5c5e42fc5a7ccd3ef443
27e17661f5573f63b65e3a5cfe5bdca75acdc1911441b032781f7ebe125d9194
feccbcb1e8c4f1e73c4029ca393d1c782434fc2a9a4f36d615845a49b458cf2c
7b7c3c662d06de7dd0bc41a6fee99cd6d460d204aab7ade67e321bebf04b7447
5c182c9ff2429f6f56952c3ddd20684aefd026f2f094ee216335186551c939b8
12ef3b455e93ac089495bbbf432a1c20c041bfde17903d154e4c730248f294f9
511d5dd4cfc7c7d5297d31bb234669fdf01b41da4b2399e039385c0b130021f4
c416052c8ac6bfb78b7f0c46c568c528ead33501149661f1d9ecb1861269f8fa
7c2a9ad5fcf489d1844f51830242f6dd9dfc203be6de3ceb07a4f6dd21c9f1a3
b13cb20a09cff9637ad665578291798ec6d4f5f4b78793d31b2cafe4def59759

# SHA1
65b0853abb656c6cc342d87b872fbe21482e9bae
938325004e44ab1a65e948b4d07b05229309f630
```

### Payload B — ABE bypass

```
# nc7d8p7u8j3n4hgm.com · efeb550a (earliest known)
ceb31976b8040cad5d5db3856466d198d3c0ea5bc904ae05c509b3b6de72e1c8

# emeditorde.com/gate/start/2daef8cd (EmEditor)
78d2244ea1c3cca2d18f754a9f0e15cabe2859817dfa803583901139764a0e6c
9bb8543453878d3390593ff76f9ab6dc8209e14f64dea51f82882309fd6ede23

# cachingdrive.com · 2daef8cd (EmEditor)
9a5be7789d31b5b0bcb92b807efffa4d96292b093921076b678a2234b30b8423
a310dcb08c77acfeda03437bc4b0f180198de9c9832df2cbb64758c82eb774c7
c0bbfb17e2817567265f46cbad61cb5922c67931c6fc2d9d59fb071fe214d411
edce6cabb33e84ffb4be9ee3377f326657e16b005f90d22267e0dfaab9561366

# olive3451.com/gate/start/f8c45bba
200646480d8b71e43aa940343ea546362565f7c61df11c9f74cec625794e9052

# mo2307.com/gate/start/550bb89b
c47610c9df3fb101b0e99f2ac12589db653464edf12cebaa2c67fd33fc7715f3

# mt7263.com/gate/(start|init|auto)/c09d19a0
ac5c6d38b45bb429b7f690530c5ffaf329193f606796c602566702450dc9099f
844c67c405eb7bdd8e61720f542eee7f87ec8470612a1dc19e332c35a174ae22
bdcfccf3e0aa2a524251c0594d3c308a940b23054374f36f2e4b73f4bc11b11d
bcb515be6344720a3b06e6bd56e5eeaa661810eb14456acceb7eab5029704117
bb78f024c4d8b5a6a128aacb498acad025a234a6b25fde36ff2e14601134555f
b37ee243518221017bab0eb4b54b5431571cc21e54113698ce49a89b89993754
65e1a542bb7d995cc4aa6c71191da125f14f99ca03da7266f5b071440d6d229a
0e8c45d847f57095d9879c0da764ab02431db4d5d85f50c4fd5ba38353b79eed

# Additional — Payload B
ff81cb9263fcde5870a0748fd6af2d30a4ba864415c15ca14827d0dd723eb60c
be2ff065a232a3a6f187f9fb03a6c1b368dff3d2ba0966777b1f5503aa5ecd16
2d7a94e4a0fedcf31cdd43b06222add9d1888fecb2c5488afc658d08c3f40116
02180bfb80498106dbe8524ab914845b9d0de62d0c3eb1112e4ce4894a0981f5
```

### Native ABE helper — Payload B (PE, 4,608 bytes)

```
54ab86b72423832e1d821e19486844375e1428079e1622f1c967d5a66bdc0b48  # x64
4563483704a8190d3ed69005fb2f593e53ca4496399e96afdb48fbde8ccdb51d  # x86

# Imphash (x64 and x86)
551c967b0ddbc198545038c596a3c10d
```

### Next-stage scripts (served via /gate/auto/f8c45bba/)

```
dae43f987ad038ee8b461066ef88956ca75e41d0a11ec258ba3ea93ac877d4d7
21ed7e38f52a58e2279950cb8f8b5ca7a7a2e3915da6406e11313b1b5a2a89cf
a156c3eb3a07e08c270435f2dd97780f394cf6f7683c045cc6866ce92c30a03b
6e2754e15f26ea4b4236f1fbc59fa926356560475349bb5f826bc3488e66e7c4
```

### Payload C — native EXE loader

```
# ms2026.zip — char-based DGA (seed 0xD01B (53275))
0858dfd8ec91942e4a40c8c40bc5602291dd909837a132a416091b5ab3f28d7f

# driver66.exe — wordlist DGA (seed 0x2507E)  imphash: b69e5fef0a591e314b65ff8477ac05be
d1b88ded80f0e616362b8984334c69da1ea2f32d0828480e32978d1a710f40c5
d57e132866286f9b4227c7fb1cd77f16a461e76a3f3e71362734741aab6b9a96

# loader_protected.exe variants  imphash: 72c11221da7236c03e879b4c984205c4
6445369559d382af2f1395c81209e59abf012ce2e22c0a835b684c92aea2b3dd
71c4d18d4729fca80a50a97bc94a7ba44a5618d38a675c7ef3c5c6561f0044e7
```

### Payload D — stealer / task-worker DLL (/avast_update)

```
149a714900952e3dc549a71dd2d001ba3226ec3a85e4ccfbd8f99c3a773fa304
PE32 DLL x86  ~7.5 MB  export: TLSDataStart
Delivered via /avast_update — confirmed active domain: gmuikyswmaosaqwk[.]xyz
```

### Other hashes

```
9c87e8162b39fbb773c416006b16f8e34aca53372d1b2d4a584df0ffc69ad333
89d634c8471382ff9c6fd966008ad5c376d7a0edae8f799eb569837170f2373d
a1c5e1d9bdc1a931c11ac6fdfdff1fbc69ff88521cf443cb174f9720a05fe72d
a6525b37b0cc5339df375e17a0c10772b50c9d425001b0c3a9dada995c7f62dd
aa350580ae5ea46544ffa15c324ab4225dff0dcc5842ac5ca8e2dc4018e5ffad
64d2a9a49e27d89f1b3489d7db29c3a3a12b4b090f59c24b694c239cb55db262
5c6a2c73f59fd8defbf118f87e5c88ba62e3067f8e8c0ed104f3f188fa0d959d
de34f2f93b74e049a08074c779a863a87a85a403594b8e220b1fba15112e6386
dfd21a363f4994794f821d76ca61c834882a51b5c6f7b95627b70789462149e3
a31ae1eef3261c36b465255e624fb7ac5899bf2a9823564ba792fac8346723aa
```

---

## Host artefacts

```
# Payload B / extension
C:\ProgramData\tmp_mojo.log
%LocalAppData%\Google Drive Caching\background.vbs

Scheduled task name:    Google Drive Caching
Browser extension name: Google Drive Caching
Scheduled task command: conhost --headless powershell -ep bypass   [PT1M]
Named pipe:             \\.\pipe\mojo.<pid>.<tid>.<hash>
Named pipe:             \\.\pipe\ArchPipe_\d{10}
Pipe handshake magic:   APPB  (0x42505041)
In-memory archive:      secure_prefs.zip

# Payload C / Payload D
%LocalAppData%\hyper-v.ver      client UUID persistence
User-Agent: cpp-httplib/0.12.1  loader network signature
loader_id: 280126               hardcoded in /tasks/get_worker body
Add-MpPreference -ExclusionPath ...\hyper-v.exe
```

---

## Code-signing certificates used by malicious installers

| Subject | Issuer | Revoked |
| --- | --- | --- |
| `WALSHAM INVESTMENTS LIMITED` | Microsoft ID Verified CS EOC CA 01 | Yes |
| `WALSHAM INVESTMENTS LIMITED` | Microsoft ID Verified CS EOC CA 02 | Yes |
| `Xiamen Quanlian Information Technology Co., Ltd.` | Sectigo | Unknown |
| `Shenzhen Xingzhongxing Electronic Technology Co., Ltd.` | Sectigo | Unknown |

---

## Routing-token index

| Token | Payload | Delivery host | Period |
| --- | --- | --- | --- |
| `efeb550a` | B | nc7d8p7u8j3n4hgm | Nov 2025 |
| `mg8heP0r` | A | emeditorgb | Dec 2025 |
| `2daef8cd` | B | emeditorde · cachingdrive | Dec 2025 |
| `e805d522` | B | keyactivate · n8n.kraski-event | Dec 2025–Jan 2026 |
| `hAUjZrJo` | A | 8mrzhrdm0obptpp | ~Jan 2026 |
| `XstQk8Ja` | A | 4kkaxgfdw7l1yvv4t9v | ~Jan 2026 |
| `WWboshwF` | A | 795n5qr4vk02wibh | ~Jan 2026 |
| `mMbcjy2q` | A | orangewater00 | Jan 2026 |
| `XYaR5gFi` | A | metrics.msft17 | Apr 2026 |
| `f8c45bba` | B | olive3451 · reshow35 | Mar–Apr 2026 |
| `eed8b732` | B | kafeprog7 | Apr 2026 |
| `98b31f0c` | B | reshow35 | Apr 2026 |
| `dIG1bXo3` | A | events.msft23 · api.bio9438 · event.dis4cle.info | Apr–May 2026 |
| `c09d19a0` | B | mt7263 | Apr–May 2026 |
| `550bb89b` | B | mo2307 | Apr–May 2026 |

---

## Sources

| Source | Link |
| --- | --- |
| Emurasoft — Security Incident Notice | https://www.emeditor.com/general/important-security-incident-notice-regarding-the-emeditor-installer-download-link/ |
| Qianxin / RedDrip Team — EmEditor supply chain incident details | https://ti.qianxin.com/blog/articles/emeditor-supply-chain-incident-details-disclosed-en/ |
| Emurasoft — Follow-up Security Incident Notice | https://www.emeditor.com/general/important-follow-up-security-incident-notice-regarding-the-emeditor-installer-download-link/ |
| Trend Micro — Watering Hole Attack Targets EmEditor Users | https://www.trendmicro.com/en_us/research/26/a/watering-hole-attack-targets-emeditor-users.html |
| ReversingLabs — Inside the EmEditor supply chain compromise | https://www.reversinglabs.com/blog/emeditor-supply-chain-compromise |
| Stormshield — Investigation on the EmEditor supply chain attack | https://www.stormshield.com/news/investigation-on-the-emeditor-supply-chain-attack/ |
| @g0njxa — Fake Mullvad VPN lure | https://x.com/g0njxa/status/2041636371790495798/ |
| @g0njxa — Fake developer tool lures | https://x.com/g0njxa/status/2041643150385553660 |
| @g0njxa — Fake Gemini CLI lure | https://x.com/g0njxa/status/2046605636494885329 |
| @g0njxa — Fake Chocolatey lure | https://x.com/g0njxa/status/2048832122618847252 |
| Ontinue — Behind a Fake Claude Code Installer | https://www.ontinue.com/resource/blog-behind-a-fake-claude-code-installer/ |
| EclecticIQ — SEO poisoning campaign — Gemini CLI and Claude Code | https://blog.eclecticiq.com/seo-poisoning-campaign-leverages-gemini-and-claude-code-impersonation-to-deliver-infostealer |
| matsudai-0603 — Static analysis of event.dis4cle.info payload | https://github.com/matsudai-0603/setup-code/blob/main/dis4cle_payload_static_report.md |
