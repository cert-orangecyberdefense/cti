On November 18, our CERT was alerted by the International CyberSOC of a phishing campaign against several of Orange Cyberdefense customers in Germany. This campaign is designed for Microsoft 365 credential harvesting.
The campaign likely started earlier this year, and has been already briefly mentioned in open sources:
- https://govcert.lu/articles/phishing-threats/20250428-1/ 
- https://www.diprotec.de/magazin/phishing-warnung-gefalschte-microsoft-e-mails-im-umlauf---unternehmen-im-visier

We were able to pivot on the given indicators, and further uncover additional insights on the campaign’s victimology, infrastructure and execution chain.
This phishing cluster leverages emails sent from compromised accounts. The emails contain a link to a subdomain of bubbleapps[.]io. Bubble.io is a no-code platform that lets users build full web applications through a visual editor instead of writing code. This platform has been regularly abused by threat actors to host phishing content since 2020.
In the campaign we observed, a large portion of these bubbleapps URLs spoof names of real German companies. It also appears this campaign targets English-speaking and Italian-speaking users.

The HTML content of the page contains a JS which launches a redirection once the victim provides their email to proceed. The second-stage redirection URL then leads to another page where a Cloudflare’s human verification-step must be carried out first. 
Next, after a supposed sign-in initiation process, the user is asked to enter their Microsoft account username and password. 
This is a standard Microsoft 365 credential phishing infection chain.
