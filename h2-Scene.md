# Cyber moves fast. 

In this assignment, we'll start following the scene. 
As part of **h2**, I've listened to a podcast, read a blog article, tried summarize them and finally science that by trying to link the theory or model from the article in [h1-Cyber Science](https://github.com/elhamIT/cyber-security-course/blob/main/h1-cyber-science.md) to the blog post and podcast episode I found here. 

## [Darknet Diaries, EP 153: Bike Index](https://darknetdiaries.com/transcript/153/)

I listened to this podcast and the reason why this topic caught my eye, is that I have had my bike stolen couple of times and it is interesting for me to dive into the world of stolen bikes. 
to get to know who does it and where do the bikes go?

Here I have gathered the summary for this podcast:

* The story starts with founder Bryan Horton, whose own bike was stolen while he was showering in college. This became the personal impetus for what would become the project.
  
* He built a free, open registry called **Bike Index** where people can report stolen bicycles (make, model, serial, photos) and buyers or shops can check if a bike is listed as stolen.
  
* Over time the registry gained traction and data volume, allowing Bryan and volunteers to observe patterns in theft and resale: bikes stolen in the U.S., listed quickly online (OfferUp, Facebook Marketplace), sometimes shipped across borders (for example to Mexico) for resale.
  
* They used _**OSINT**_ (an open-source intelligence) techniques: scrutinizing listing photos, metadata slip‐ups (folder names showing, house numbers in background), geo-clues, and built evidence to partner with local police.
  
* Despite evidence and federal indictments (in the U.S.) against a U.S. "middle-man" seller, the main ringleader in Mexico continued selling bikes online unabated, pointing to gaps in law-enforcement, platform moderation and cross-border enforcement.
  
* The podcast emphasises how the stolen-bike trade has a defined supply chain: from theft to staging or storage, online listing, resale domestically and even across the border. Bryan describes how an operation once sourcing from the Bay Area shifted to San Diego and beyond.

## [Schneier on Security, Autonomous AI Hacking and the Future of Cybersecurity](https://www.schneier.com/blog/archives/2025/10/autonomous-ai-hacking-and-the-future-of-cybersecurity.html)

I read this blog article since the topic sound quite interesting to me and I have summarized it:

* AI agents in hacking are now emerging at speed, scale and sophistication: they automate reconnaissance, exploitation, credential theft, even ransom demands.
  
* Here are some examples: an AI company submitted  ove 1,000 new vulnerabilities via bug-bounty in a few months or DARPA’s AI Cyber Challenge found 54 new vulnerabilities in four hours.
  
* In one case, Russian malware used an LLM to generate both reconnaissance and data-theft commands in real time.
  
* On the defense side: AI isn’t just a threat, it could empower vulnerability research, automated patching, and new operational models (e.g., "VulnOps", "continuous discovery or continuous repair").
  
* Several future phases are outlined as follows: 
  * Phase 1: AI augments vulnerability researchers. 
  * Phase 2: Emergence of "VulnOps" pipelines akin to DevOps. 
  * Phase 3: AI-powered security becomes embedded in software development (CD/CR). 
  * Phase 4: Self-healing networks where AI discovers and patches vulnerabilities autonomously, but with many risks (liability, vendor relationships, correctness).

* The key warning here is that: The attacker-defender balance is at risk of shifting dramatically in favour of attackers unless defenders adopt corresponding shifts.

## Linking the pieces to each other

Here, I try to make a linkage across theory, models, and recent security events connecting the article I read and summarized in [h1-Cyber Science](https://github.com/elhamIT/cyber-security-course/blob/main/h1-cyber-science.md), blog post, and podcast, showing that how they all feed into a bigger security picture.

**Putting the puzzle together:**

In summary:

* The DevSecOps article gives a structured model for integrating security into software development.

* The blog post sets the threat horizon: autonomous AI hacking demands change in how we develop and deploy software securely.

* The podcast illustrates that even physical and analogue assets face supply-chain and asset-tracking issues.

_**Theory or Model:**_ A multi‑vocal literature review (2024) presents a CPTM model (Challenge‐Practice‐Tool‐Metric) for understanding how security is integrated into software development via DevSecOps:

  * It identifies key dimensions: Definitions, Challenges, Practices, Tools and Technologies, Metrics and Measurement.
  * It emphasises that organisations often struggle with: culture and people, process integration, tooling maturity, measurement of security outcomes.

* From the article’s CPTM framework: The "Tools and Technologies" and "Metrics and Measurement" dimensions speak directly to the blog’s theme of AI-powered attack tools and the need to measure and defend against them.

* The "Challenges" dimension in the article (culture, process, tool integration) aligns with both the blog (teams needing to adapt to autonomous AI attacks) and the podcast (non-security teams, marketplaces, asset owners needing culture, process and technology changes).

* The podcast introduces the supply chain, asset registry and leakage path narrative: stolen bikes → listing → resale, which mirrors software development assets → vulnerabilities → probe → exploit in the blog.

* The blog shows a future threat vector (autonomous AI hackers) while the article provides a framework for organisations to integrate security practices into their pipelines and suggesting that DevSecOps structures must evolve to handle AI-driven threats.

* The podcast gives a concrete scenario of how weak processes, tools and measurement (marketplace oversight, asset tracking) lead to successful criminal operations. Therefore, illustrating the article’s model in action in a physical-digital analogy.

## Fresh Security Event in this Context

For this purpose, I have considered this recent event: Palo Alto Networks launching new agentic AI-powered security platforms in October 2025 (Cortex Cloud 2.0 / Prisma AIRS 2.0) to counter the very threat described in the blog. 

* This event shows a tool and technology response to autonomous AI hacking.

* It reinforces that organisations are recognising the "Tools and Technologies" dimension in the CPTM model, upgrading their pipelines and security tooling.

* But it also shows a gap: the article says measurement and metrics and global, process and culture issues are weak, and we need evaluation of these tools, metrics to show their effectiveness, and process and culture adoption.

* Thus, this event sits at the junction: theory (DevSecOps model), threat (autonomous AI hacking), and practical response (new AI security platforms).

## References
* https://terokarvinen.com/cyber-security/
* https://github.com/elhamIT/cyber-security-course/blob/main/h1-cyber-science.md
* https://darknetdiaries.com/
* https://darknetdiaries.com/transcript/153/
* https://www.schneier.com/
* https://www.schneier.com/blog/archives/2025/10/autonomous-ai-hacking-and-the-future-of-cybersecurity.html
