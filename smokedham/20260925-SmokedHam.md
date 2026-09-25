🧶Our CyberSOC team has observed malicious ads leading to fake RDC Manager or RVtools training websites. These sites deliver fake installers that lead to various payloads, including **SmokedHam/UNC2465**.

🔗 Other payloads using the same signer, SAN SOFTWARE, TOO, have also been documented recently but not formally tied to this cluster:

https://malbearlabs.com/posts/novel-malware-built-to-survive-the-analyst
https://arcticwolf.com/resources/blog/clickfix-campaign-exploits-powershell-loader-with-identifier-obfuscation-for-malicious-activity/

| IoC                                                              | Comment              |
|:-----------------------------------------------------------------|:---------------------|
| 04f242216723ab58bdc7eeb8c2b1166c8a4c441a236d7f0a2ffced52ab6f40f2 | Fake installers      |
| 083a6e878a4568704373bca7e64b571ed10f6d00313b572b95e165987033d73e | Fake installers      |
| 1520eb88f590ad1ca0266a477a997e6e9d166329d32c199e5f9ea5cae336fff8 | Fake installers      |
| 15c5c8655f588ab51c16d34fd68de481923350908b3d555f2fa9cb78605f6f0f | Fake installers      |
| 19033e2400ffa9b542a8e7e4d3a346304426c076e64bd38abafca475cfe81c6e | Fake installers      |
| 23b06656beb0eed496a758cfc4da8a450ae4e102390e4008acc5e876f03ab076 | Fake installers      |
| 2ce87b7eac46f38f5ab2dbe87e325a46fe7d6009677d2d628b70847862b93721 | Fake installers      |
| 2f294991f052b452c83b27be2467028cd813efc059e4bbcf0dc67c78f5c31803 | Fake installers      |
| 2fe416bf711cc23389e5073052a209a46f76088f595d8b508dcf91f4ad4ef5a1 | Fake installers      |
| 3008b1af19b0a2e8a3978474f93b47bd01c81bcd41b57d7091ed507f438a3d44 | Fake installers      |
| 322b27ee55c220a65feaafe5592e5938f9d1ca99407a14f1d9bad3b10ce5a185 | Fake installers      |
| 44e2abe37e09ddab75c89dcfb20017836ef07dfe2afba7aa3d2470c587d0c90a | Fake installers      |
| 47ec5bedbb2eeea0ff822f9328d65e305a0e9567017f6bc2f7c5c9c844c2f743 | Fake installers      |
| 49d7455d88aedfbb61e8db93a6719331c1e10b1f7d3e149f78d3e198fa73f182 | Fake installers      |
| 4bb5874756ee936ddbb02d110a4ff1c273496caaa43531e353a0cadaf4c7fabd | Fake installers      |
| 4eae41b58755065ebc795ffdfd815615f8b6463bc235001f8467fb4627731a14 | Fake installers      |
| 52391bbd71aa48788e3a80433ad4b983f027cfedddb19bc57484482858d3c6bf | Fake installers      |
| 52e9f89e99ddb061865bb0393bf8a078c6c2d49bd6600eb67031d87e349bc324 | Fake installers      |
| 52fc05eab8c6ca01b80ead7abecbb3409b0960766e4fe503ea9e187d41ccc8e4 | Fake installers      |
| 53fefa3f2ab3647760c97723d777e4b4e2645aa0e54802116342e456748f66be | Fake installers      |
| 5681219ac0dbc8a821d57e7d607b363cba809850f014d1009af7a5c3187445e2 | Fake installers      |
| 5714e91499a84e2bee30d158e652fd6931e429680f5b663b93f21ed521b6e702 | Fake installers      |
| 574d22382502ca1cbadf7346503d29746fc34ebd1365419c70c38e93c3bb4397 | Fake installers      |
| 58f9576f20a0dde75a66dfbc005a743cbafc0eb234d98b8ae96d731a83fdc618 | Fake installers      |
| 5a4a69142c1284103e31932ce7b3b228744cff5f6fdeed9bcf18c6c2df7346be | Fake installers      |
| 5afc5a103247e4a64155ada9d9f5ebd65073f7c17dd396bc054acdbaaa01fb60 | Fake installers      |
| 5e002371d316d7b3d0800004cd91e0885e78c346212a79f6dbd3de22b141eae8 | Fake installers      |
| 605acaf6d11c883c24960bedc6e111a37555a57595b43b1b0d9f606ce24131f6 | Fake installers      |
| 62d36a8b009bd696fa2677e055442115744c71104a8cdd9387004abf49b8add0 | Fake installers      |
| 64d8663e0abab7c027e054bbd184080a2c6dfec6fd49923eb7de119bda983a5a | Fake installers      |
| 66ac4f99531121c3150e81b41ed55806396ebcfe070d319fc7e47e32dac42722 | Fake installers      |
| 6eb1a21873d7c0f49da454620f1aa72a28409176cb3286aa7c4b5c306037eb0e | Fake installers      |
| 79054d89f1d88053df39fd532ae53850f34d02b28d3a6b0b7ad757277bfe31b8 | Fake installers      |
| 83e297cd50a7076d445707cb91812d432a039a2721aae31088dd3913bcdbd781 | Fake installers      |
| 8e7cec1d8926dac100ae836d15251e421067fc2f30146524513fbf79b02a1888 | Fake installers      |
| 8ec708f67d835c9099f495fe3de48bb149dfc720ca2e49d3a495f34166100331 | Fake installers      |
| 90c808a56d75d1b1e120df25c6b374fd303840a85da96819d4f4ce30da7bd08e | Fake installers      |
| 92b70318e5aab13d5b3a71c2542b08b84b1f783462c94537391f2a1c2483dc07 | Fake installers      |
| 9960b5d9dc475dc0fd1b73d72ba11ee788b7eff294f5c44f8828575999eddc09 | Fake installers      |
| 9a734d2ca2bfa99041fdb2ce1263bf774013085a6ae1b0022b831bbf39d92e35 | Fake installers      |
| 9bd968998e4e62305d16c067a95eee2b1ab951c40631037b0ee97708b653f476 | Fake installers      |
| a3106510447ea3959f9eb70258d979e4001940afd64ed1ee7591f6eff34a2cd3 | Fake installers      |
| aa5bf14799616a7dd042939c0768c5e529b0e21f841cd6334d7150f75766dee4 | Fake installers      |
| caf8d930c13e70928571a66202bdc53fc56c4f4122c8c012aaf3e923ccca7f05 | Fake installers      |
| d80dc67dbb28ce79425acb503aeec7cc73462dcfe456e4ccdc80618a81e9e8ce | Fake installers      |
| d91fbb7372da518d3cae8714cc6dc3b1f3ca3acaf13ae761e0a04116b18ff4cf | Fake installers      |
| db570fab695d7d8572a920d6e33e8107259e1bc3c00eda45c4b0da72687ffc8d | Fake installers      |
| e2c8bdd7320363a6f467bae417e758de255f485d7b825c209f105b7d5483e3f3 | Fake installers      |
| e5224919f3e29215e1a27daf603764b7ab0957b611c9cf76edc721b60e20b607 | Fake installers      |
| e5620a84b616cb1a947a4cc9005af0c5b582e09350a08ebec639b93f03e3a01e | Fake installers      |
| f241db1bf213abecdefd6aec12afa27d93ff0f6ef87f64e0faa27414b9b6a2fa | Fake installers      |
| f85a5c2f200ead6e25775ad2350405acd98746d236f07a15d6f99f0d467172a5 | Fake installers      |
| f8778f545a9a02318b394d2df542af385820d1031100939fc9d277c2e0ee258d | Fake installers      |
| remopla[.]net                                                    | Potential C2 Domains |
| chromora[.]net                                                   | Potential C2 Domains |
| xoludet[.]net                                                    | Potential C2 Domains |
| sewolud[.]net                                                    | Potential C2 Domains |
| wiperon[.]net                                                    | Potential C2 Domains |
| kloders[.]net                                                    | Potential C2 Domains |
| baserde[.]net                                                    | Potential C2 Domains |
| remuloz[.]net                                                    | Potential C2 Domains |
| 192[.]227[.]231[.]14                                             | Potential C2 IP      |
| 167[.]148[.]201[.]90                                             | Potential C2 IP      |
| 167[.]148[.]201[.]189                                            | Potential C2 IP      |
| 69[.]48[.]228[.]49                                               | Potential C2 IP      |
| 217[.]17[.]97[.]49                                               | Potential C2 IP      |
| rough-base-bddc[.]web-static-4jf[.]workers[.]dev                 | SmokedHam C2         |
| 45[.]94[.]31[.]112                                               | Cobalt Strike C2     |
| rdc-man[.]app                                                    | Delivery domains     |
| rdcmandev[.]app                                                  | Delivery domains     |
| rvmetric[.]app                                                   | Delivery domains     |
| rvtoolenterprise[.]com                                           | Delivery domains     |
| rvtoolsai[.]com                                                  | Delivery domains     |
| rvtoolis[.]info                                                  | Delivery domains     |
| rvtoolz[.]info                                                   | Delivery domains     |
| rvtoollsi[.]com                                                  | Delivery domains     |
| rvtoolso[.]info                                                  | Delivery domains     |
| rvtoollsa[.]com                                                  | Delivery domains     |
| rvtoolc[.]info                                                   | Delivery domains     |
| rvtoolsit[.]com                                                  | Delivery domains     |
| rvtoolson[.]info                                                 | Delivery domains     |
| rvtoolsrun[.]com                                                 | Delivery domains     |
| rvtoolsmax[.]com                                                 | Delivery domains     |
| rvtoolsuk[.]com                                                  | Delivery domains     |
| rvtoolsgo[.]com                                                  | Delivery domains     |
| rvtoolsbox[.]com                                                 | Delivery domains     |
| rvtooik[.]com                                                    | Delivery domains     |
| rvtoolsone[.]com                                                 | Delivery domains     |
| rvtoolseu[.]com                                                  | Delivery domains     |
| rvtoolsup[.]com                                                  | Delivery domains     |
| rvtoolslab[.]com                                                 | Delivery domains     |
| rvtoolsnow[.]com                                                 | Delivery domains     |
| rvtools-cloud[.]com                                              | Delivery domains     |
| www[.]rvtools-dev[.]com                                          | Delivery domains     |
| rvtools-get[.]github[.]io                                        | Delivery domains     |


