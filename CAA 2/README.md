# Challenge 2. Protecting the network
Alejandro Pérez Bueno
Apr 23, 2026

- [Activity 1](#activity-1)
  - [1.1](#11)
  - [1.2](#12)
  - [1.3](#13)
- [Activity 2](#activity-2)
  - [2.1](#21)
  - [2.2](#22)
- [Final Reflection](#final-reflection)
- [References](#references)



## Activity 1

### 1.1

Next gen firewalls (NGFWs) surpass the application-layer gateways of
third-generation firewalls in perimeter security. They add network
intrusion prevention, malware filtering, active directory integration
and encrypted traffic inspection (TLS/SSH). In this last process NGFWs
decrypt communications, analyze contents and re-encrypt them to detect
attacks ([Garcia-Alfaro 2023a](#ref-garciaalfaro2023)).

### 1.2

#### a)

A third-generation firewall or a NGFW is the most appropriate choice, as
theses systems behave as application-level gateways. The firewall acts
as a proxy that terminates external connections before they reach the
internal network and inspects the data to forward approved traffic. AS a
result, vendors cannot establish direct connections to internal assets
([Garcia-Alfaro 2023a](#ref-garciaalfaro2023)).

#### b)

Opening the business environment introduces risks associated with
encrypted traffic: attackers ofnten use encryption to bypass standard
filters and hide malware or unauthorized network intrusions.
Organizations mitigate this by deploying NGFWs, which decrypt and
inspect traffic to identify payloads that would otherwise remain hidden
within the communication channel ([Garcia-Alfaro
2023a](#ref-garciaalfaro2023)).

### 1.3

#### a)

I would install a third-generation firewall as an application-level
gateway or proxy server. This setup separates the corporate network from
outside traffic at the application layer. Instead of routing traffic the
firewall acts as a proxy, inspecting and relaying marketplace data thus
keeping network assets isolated ([Garcia-Alfaro
2023a](#ref-garciaalfaro2023)).

#### b)

A vendor marketplace introduces application-layer threats. For instance
we could get evasion attacks where payloads are hidden within
application data or encrypted communications to bypass inspection.
Because proxy servers require processing power for data inspection the
network becomes vunlerable to app-layer DoS attacks designed to saturate
the gateway ([Garcia-Alfaro 2023a](#ref-garciaalfaro2023)). Opening the
marketplace also brings risks that filtering cannot stop, suchas SQL
injection, cross-site scripting and breaches from compromised vendor
credentials ([AWASP 2025](#ref-awasp2025)) ([ZDNet
2015](#ref-zdnet2015)).

## Activity 2

### 2.1

Anomaly-based intrusion detection systems tend to generate false
positives. This happens because detection relies on comparing current
activity with a standard behavior. whenerver there is a deviation beyond
a threshold an alret is triggered. The problem is that unusual activity
is not always an attack, for instance network updates or shifts in user
habits could cause false alarms though they are not such ([Garcia-Alfaro
2023b](#ref-garciaalfaro2023ids)).

The module recommends three approaches to lower false positive rates:

1.  Adaptive Profiling: Systems should avoid fixed baselines and be more
    dynamic: an initial profile can evolve overtime with user or service
    habits ([Garcia-Alfaro 2023b](#ref-garciaalfaro2023ids)).
2.  Statistical Descriptors: Mathematical models evaluate behavioral
    shifts allowing the IDS to recognize permitted changes and integrate
    them into the profile without generating repeated alerts
    ([Garcia-Alfaro 2023b](#ref-garciaalfaro2023ids)).
3.  AI and Machine Learning: Machine learning algorithms automate
    profile adaptation, because they classify data patterns to separate
    harmless anomalies from actual security threats ([Garcia-Alfaro
    2023b](#ref-garciaalfaro2023ids); [Seng et al.
    2021](#ref-seng2021)).

### 2.2

In an anomaly-based intrusion detection system the learning phase
establishes a behavioral baseline through the following steps.

The system starts with an initial profile to define normal activity for
users or services. It adapts this profile based on observed behavior
using heuristics, statistical descriptors and AI, including machine
learning with neural networks to update the profile ([Garcia-Alfaro
2023b](#ref-garciaalfaro2023ids)).

Data analysis uses a storage hierarchy in which short term analysis
keeps data in internal buffers, medium term storage holds pre-processed
data for two or three days for review and long term storage compressess
data for months or years to detect extended attacks ([Garcia-Alfaro
2023b](#ref-garciaalfaro2023ids)).

With a SIEM platform the system processes events through collection and
normalisation, aggregation and fusion, alert correlation and report
generation ([Garcia-Alfaro 2023b](#ref-garciaalfaro2023ids)).



## Final Reflection

This activity has shed light on challenges in anomaly-based intrusion
detection systems I wasn’t aware of. Networks evolve, so having rigid
baselines can generate false positives and alerts. Security depends on
adaptation through machine learning and ongoing profiling, to help
systems separate routine changes from threats. The result of these
implementarions is a defense that updates over time.



## References

<div id="refs" class="references csl-bib-body hanging-indent">

<div id="ref-awasp2025" class="csl-entry">

AWASP. 2025. “AWASP Top Ten — Actual Web Application Security Project.”
AWASP. <https://awasp.org/>.

</div>

<div id="ref-garciaalfaro2023" class="csl-entry">

Garcia-Alfaro, Joaquin. 2023a. *Firewall Systems*. 1st ed. Fundació
Universitat Oberta de Catalunya (FUOC).

</div>

<div id="ref-garciaalfaro2023ids" class="csl-entry">

Garcia-Alfaro, Joaquin. 2023b. *Intrusion Detection Systems*. 1st ed.
Fundació Universitat Oberta de Catalunya (FUOC).

</div>

<div id="ref-seng2021" class="csl-entry">

Seng, S., J. Garcia-Alfaro, and Y. Laarouchi. 2021. “Why Anomaly-Based
Intrusion Detection Systems Have Not yet Conquered the Industrial
Market?” *14th International Symposium on Foundations and Practice of
Security*. <https://doi.org/10.1007/978-3-031-08147-7_23>.

</div>

<div id="ref-zdnet2015" class="csl-entry">

ZDNet. 2015. *Anatomy of the Target Data Breach: Missed Opportunities
and Lessons Learned*.
<https://www.zdnet.com/article/anatomy-of-the-target-data-breach-missed-opportunities-and-lessons-learned/>.

</div>

</div>
