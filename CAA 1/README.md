# Challenge 1. An overview of cybersecurity
Alejandro Pérez Bueno
Mar 26, 2026

- [Exercise 1](#exercise-1)
  - [1.1](#11)
  - [1.2](#12)
  - [1.3](#13)
- [Exercise 2](#exercise-2)
  - [2.1](#21)
  - [2.2](#22)
  - [2.3](#23)
- [Exercise 3](#exercise-3)
  - [3.1](#31)
  - [3.2](#32)
  - [3.3](#33)
- [Final Reflection](#final-reflection)
- [Personal Reflection](#personal-reflection)
- [References](#references)



## Exercise 1

### 1.1

#### Strengths

- We observe that AI-driven systems process vast telemetry volumes in
  real time, pinpointing zero-day attacks and behavioral anomalies while
  cutting detection and response times substantially.
- These systems further amplify security teams’ efforts through
  autonomous alert triage and large-scale patch deployment. ([Yerabolu
  2025](#ref-yerabolu2025))

#### Weaknesses

- Employees’ unchecked use of generative AI for routine tasks often
  bypasses IT controlls, invreasing risks of data leaks and regulatory
  violations.
- Many AI models offer little to no transparency (thay are a black box),
  complicating security teams’ ability to assess risks, audit decisions,
  or interpret anomalous outputs. ([Durbin 2025](#ref-durbin2025);
  [National Institute of Standards and Technology 2023](#ref-nist2023))

#### Opportunities

- There is potential in AI tools that monitor evolving regulations like
  the EU AI Act, automatically refining internal policies and easing
  audits.
- Digital twins powered by AI, alongside cyber risk modeling, allow
  CISOs to simulate attacks, probe weakneses and allocate resources by
  weighing financial outcomes. ([Boston Consulting Group
  2024](#ref-bcg2024); [Kovrr 2026](#ref-kovrr2026))

#### Threats

- Malicious actors exploit AI to craft adaptive payloads, mask command
  channels, and execute rapid, multi-phase network breaches.
- Adversaries harness AI for tailored phishing and deepfake fraud,
  overwhelming conventional defenses. ([Carpenter
  2025](#ref-carpenter2025))

### 1.2

Post-Quantum Cryptography (PQC) involves developing algorithms that
operate on standard hardware yet resist attacks from classical and
quantum computers. It aims to replace vulnerable standards like RSA and
ECC before Shor’s algorithm enables quantum decryption. Urgency arises
from “Harvest Now, Decrypt Later” threats, where attackers store
encrypted data for future cracking. Adopting NIST standards such as
ML-KEM and ML-DSA secures communications and preserves data sovereignty
([NIST 2024](#ref-nist2024); [Telefónica Tech
2025](#ref-telefonica2025)).

Below we propose an exaple transition to post quantum cryptography:

First of all, we will form a cross-functional cryptographic steering
committee with InfoSec, IT, legal, privacy, and procurement
representatives to oversee the transition, as quantum migration demands
executive support for budgets, policy updates, and strategy across
units. Then we will use automated tools to inventory all cryptographic
elements in networks, code, and hardware, enabling identification of
vulnerable ciphers and a targeted migration plan that avoids disrupting
dependencies ([Palo Alto Networks 2026](#ref-paloalto2026)).

After this we will prioritize systems by data sensitivity and lifespan
via the Mosca Inequality (Shelf Life + Migration Time \> Quantum Threat
Time) focusing firts on long-term assets like records and IP to reduce
exposure from HNDL attacks ([QRAMM 2024](#ref-qramm2024); [Jena
2025](#ref-jena2025)).

Finally, we will modularize cryptographic functions and pilot hybrid
schemes blending classical (ECDHE) and PQC (ML-KEM/Kyber) exchanges,
ensuring seamless updates, compliance, and quantum resistance during
transition ([Jena 2025](#ref-jena2025)).

### 1.3

The Digital Operational Resilience Act (DORA) establishes a unified
cybersecurity and ICT risk management framework for the EU financial
sector ([IBM 2024](#ref-ibm_dora)). We observe that it shifts focus from
financial buffers to operational stability in disruptions ([PwC
2024](#ref-pwc_dora)). DORA sets standards for incident reporting,
resilience testing and informattion sharing to address cyber threats
([PwC 2024](#ref-pwc_dora)). It also oversees critical third-party ICT
providers ([Bureau Veritas 2024](#ref-bureau_dora)).

DORA covers the EU financial sector, including banks, investment firms,
payment institutions and insurance companies ([IBM
2024](#ref-ibm_dora)). We note its direct regulation of critical
third-party ICT providers, such as cloud platforms and data centers
([Bureau Veritas 2024](#ref-bureau_dora)).

Financial entities must adopt ICT risk frameworkd and monitor technology
suppliers which demands compliance investments ([PwC
2024](#ref-pwc_dora)). Meanwhile critical thirdparty ICT providers face
EU oversight and penalties for non-compliance ([IBM
2024](#ref-ibm_dora)).

## Exercise 2

### 2.1

A Security Operations Center (SOC) is a centralized entitu that brings
peoplo together to monitor and respond to cybersecurity threats in real
time ([Oguntoyinbo 2025](#ref-oguntoyinbo2025)). A SOC uses specialized
tools to analyze data across networks, track suspicious behavior and
address vulnerabilities before they can be exploited \[Wikipedia
([2015](#ref-wikipedia2015)).

The role of a SOC becomes critical to maintain business continuity. An
actual example of tihs is the UK National Health Service response to the
2017 WannaCry ransomware attack. Aftre the incident happened the
organization established a dedicated SOC to provide continuous network
monitoring, threat intelligence sharing, and rapid incident response
capabilities. By doing all this the health system significantly improved
its ability to block millions of suspicious transactions and respond
faster to future threats ([GlobalData 2020](#ref-globaldata2020)).

### 2.2

> [!TIP]
>
> Victim collapse attacks overwhelm a machine’s resources, often by
> flooding it with unmanageable requests.

- A Smurf attack uses a network’s broadcast address as a springboard. An
  example could be spoofing a victim’s IP so all network devices
  simultaneously flood the victim with ping replies.
- A TCP/SYN flood attack initiates incomplete TCP connections. One such
  example could be continuously sending SYN packets to fill a web
  server’s connection queue in order tp block legitimate users.
- Teardrop attack: misuses IP fragmentation, for example by sending
  overlapping malformed packet fragments that crash the target’s
  operating system during reconstruction
- Finally, Snork attacks cross Unix services by for instance spoofing
  requests between the chargen and echo ports to trap the victim in an
  endless loop of traffic.

([Martínez Ballesté and Mir Rubio 2023, sec. 2.4.1](#ref-martinez2023))

### 2.3

To detect a denial of service attack a SOC needs network monitoring
tools. One of these could be a Security Information and Event Management
(SIEM) platform, to aggregate logs to flag traffic spikes. Intrusion
Detection Systems also help analyze packet data to spot attack
signatures which cab be helpful in preventing DoS attacks. Other
mitigations include rate limiting restricts connections from sources
sending too many requests, using a web app firewall to block
unauthorized traffic at the application layer or use load balancers to
distribute incoming data across server clusters to prevent resource
exhaustion.

## Exercise 3

### 3.1

The attack on Energía XXI was a supply chain compromise targeting an
external sales provider. Attackers managed to steal login credentials of
this third party. With them the intruders bypassed standard perimeter
defenses and gained direct access to the commercial platform. Because
they appeared as authorized users they were able to navigate the system
and execute many database queries to scrape customer records. They then
exported files containing the personal and financial details of the
users.

([La Vanguardia 2026](#ref-energia2026))

### 3.2

The incident could cause reputational damage and lead to customers
losing interest or trust int he company. It could also carry financial
and legal impacts, with even potential lawsuits and fines for GDPR
violations.

As the company CISO I would have activated the communication plan. I
would have notified the AEPD explaining how deep the breach had been,
what data had been compromised and the mitigation actions taken. I would
have also reported the event to national cybersecurity entities like
INCIBE. As for transparency with our clients, I would have issued
communications via email explaining directly what happened, what data
had been exposed, and would have provided instructions to prevent fraud.

### 3.3

To prevent and detect this type of intrusion, I would enforce
multi-factor authentication for all internal and third-party access. I
would apply the principle of least privilege to restrict data visibility
and monitor the network for mass data exports. Routine security audits
on external providers are also necessary.

A SIEM solution would have helped detect the attack. It aggregates logs
from multiple systems to identify abnormal behavior. Even if the
attackers used valid stolen credentials, a SIEM could have flagged
logins from unusual locations or detected unusually large database
queries. This would generate alerts, allowing the security team to block
the connection before the data was exfiltrated.



## Final Reflection

## Personal Reflection

This firsdt CAA has showed me how cybersecurity is a kind of balance
between emerging technologies with persistent risks. I have also learned
that AI can speed up threat detection but also introduces transparency
issues and misuse potential. The PQC transition has reminded me that we
need structured planning against ever-so-close quantum threats, using
tools like inventories and hybrid schemes. Regulations like DORA (which
granted I did not know of) emphasize operational resilience and
third-party oversight in finance.

Handling unexpected incidents such as the Energía XXI breach, has
reinforced my conviction that every system needs to implement a SIEM (I
work at Telefónica and this is a must) for anomaly detection, as well as
SOCs for real-time response to these attacks, as seen in cases like
WannaCry from 207.

All in all, in my personal life this practice will help me take action
in protecting myself in the digital space with steps like using MFA
whenerver possible, applying the least privileges principle or just
staying more informed of when breaches occur (apparently they do much
more often than I thought).



## References

<div id="refs" class="references csl-bib-body hanging-indent"
entry-spacing="0">

<div id="ref-bcg2024" class="csl-entry">

Boston Consulting Group. 2024. “Managing Risks and Accelerating the AI
Transformation.” *Executive Perspectives*.

</div>

<div id="ref-bureau_dora" class="csl-entry">

Bureau Veritas. 2024. “A Summary of the New DORA Legislation - 9
Questions & Answers.” Bureau Veritas. 2024.
<https://cybersecurity.bureauveritas.com/dora-legislation-summary>.

</div>

<div id="ref-carpenter2025" class="csl-entry">

Carpenter, Perry. 2025. “AI, Deepfakes, and the Future of Financial
Deception.” SEC Investor Advisory Committee.

</div>

<div id="ref-durbin2025" class="csl-entry">

Durbin, Steve. 2025. “Shadow AI: The Hidden Risk in AI Adoption.”
Cybersecurity Magazine. 2025.
<https://cybersecurity-magazine.com/shadow-ai-the-hidden-risk-in-ai-adoption/>.

</div>

<div id="ref-globaldata2020" class="csl-entry">

GlobalData. 2020. “Cybersecurity in Medical.”

</div>

<div id="ref-ibm_dora" class="csl-entry">

IBM. 2024. “What Is the Digital Operational Resilience Act (DORA)?” IBM.
2024. <https://www.ibm.com/topics/dora>.

</div>

<div id="ref-jena2025" class="csl-entry">

Jena, Jyotirmay. 2025. “The Quantum Security Deadline: Building
Crypto-Agility Against Harvest Now, Decrypt Later’ Threats.”
<https://doi.org/10.37745/ejcsit.2013/vol13n523552>.

</div>

<div id="ref-kovrr2026" class="csl-entry">

Kovrr. 2026. “EU AI Act Compliance Guide for CISOs & GRC Leaders.”
Kovrr. 2026.
<https://www.kovrr.com/blog-post/eu-ai-act-compliance-explained-for-cisos-and-grc-leaders>.

</div>

<div id="ref-energia2026" class="csl-entry">

La Vanguardia. 2026. “Energía XXI Notifica Un Ciberataque Que Compromete
Datos de Contratos y DNIs de Sus Clientes.” La Vanguardia. 2026.
<https://www.lavanguardia.com/economia/20260111/11428973/energia-xxi-notifica-ciberataque-compromete-datos-contratos-dnis-clientes.html>.

</div>

<div id="ref-martinez2023" class="csl-entry">

Martínez Ballesté, Antoni, and Juan Mir Rubio. 2023. *Introduction to
Computer Security*. Fundació Universitat Oberta de Catalunya (FUOC).

</div>

<div id="ref-nist2023" class="csl-entry">

National Institute of Standards and Technology. 2023. “Artificial
Intelligence Risk Management Framework (AI RMF 1.0).” NIST AI 100-1.
U.S. Department of Commerce.

</div>

<div id="ref-nist2024" class="csl-entry">

NIST. 2024. “Post-Quantum Cryptography \| CSRC.” National Institute of
Standards; Technology. 2024.
<https://csrc.nist.gov/projects/post-quantum-cryptography>.

</div>

<div id="ref-oguntoyinbo2025" class="csl-entry">

Oguntoyinbo, Mayowa. 2025. “Mitigating the Risk as SOC Alert Analyst and
Incident Responder.” Savonia University of Applied Sciences.

</div>

<div id="ref-paloalto2026" class="csl-entry">

Palo Alto Networks. 2026. “Cryptographic Agility: The Key to Quantum
Readiness.” Palo Alto Networks. 2026.
<https://www.paloaltonetworks.com/cyberpedia/what-is-cryptographic-agility>.

</div>

<div id="ref-pwc_dora" class="csl-entry">

PwC. 2024. “Digital Operational Resilience Act (DORA).” PwC. 2024.
<https://www.pwc.com/mt/en/services/digital-services/dora.html>.

</div>

<div id="ref-qramm2024" class="csl-entry">

QRAMM. 2024. “Quantum Risk Management: Assessing and Mitigating Quantum
Computing Threats.” CyberSecurity NonProfit (CSNP). 2024.
<https://qramm.org/learn/quantum-risk-management.html>.

</div>

<div id="ref-telefonica2025" class="csl-entry">

Telefónica Tech. 2025. “Strategic Preparation for Post-Quantum
Cryptography.”

</div>

<div id="ref-wikipedia2015" class="csl-entry">

Wikipedia. 2015. “Centro de Operaciones de Seguridad.” Wikipedia. 2015.
<https://es.wikipedia.org/wiki/Centro_de_operaciones_de_seguridad>.

</div>

<div id="ref-yerabolu2025" class="csl-entry">

Yerabolu, Malleswar Reddy. 2025. “The Evolution of AI-Driven Threat
Hunting: A Technical Deep Dive into Modern Cybersecurity.” *European
Journal of Computer Science and Information Technology* 13 (7): 36–49.

</div>

</div>
