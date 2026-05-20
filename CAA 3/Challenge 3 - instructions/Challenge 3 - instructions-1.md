![Image](artifacts/image_000000_e97459dc2096406956ed062d9724516353c5d9975a3912e55259be66f144b59b.png)

UOC

## Security in Computer Networks

## Challenge 3. Protecting communications and applications

As  you  already  know,  NexusLifePharma  is  an  e-commerce  platform  that  manages  highly sensitive  data  like  medical  prescriptions  (health  data),  bank  transactions,  and  customer personal data. As a security architect, you must address the following critical issues identified in the current infrastructure.

## Activity 1. Secure communication design

For decades, the web has relied on communication via the HTTP protocol between the client (browser)  and  the  server.  However,  this  protocol  was  originally  designed  without  security mechanisms, and communication travels in plain text. To address these shortcomings, HTTPS was  introduced,  adding  a  layer  of  security  over  HTTP  through  the  use  of  TLS,  which  is described in the course materials.

In  fact,  the  vast  majority  of  current  websites  use  HTTPS.  Furthermore,  modern  browsers display explicit warnings when a site does not use HTTPS. However, communication with the NexusLifePharma website is via HTTP today, which means the server is not authenticated and the communication is not encrypted. In PR4, you must configure the web server to serve the website using the HTTPS protocol, which resolves these issues.

Explain, both theoretically and visually, how the TLS (Transport Layer Security) protocol works to address current security vulnerabilities. Your answer must cover the following mandatory points:

1. TLS Handshake diagram: Draw or show the message flow between the client (browser) and the server.
2. Fill  out  the  following  table  by  analyzing  the  cryptographic  primitives.  Explain which technique is used in each phase.

![Image](artifacts/image_000001_7bf94298fc169d91ca02b761cb6cae006781b0a8e0bbbf6bb231b9872638b30d.png)

UOC

| Phase          | cryptographic primitives                                                     | Function   |
|----------------|------------------------------------------------------------------------------|------------|
| Authentication | Asymmetric Cryptography Digital Signature with digital certificates (X.509)  |            |
| Key Exchange   | Diffie-Hellman or RSA to generate an ephemeral session key (Forward Secrecy) |            |
| Data Ciphering | Symmetric Cryptography (AES-256)                                             |            |
| Integrity      | Hash Functions (HMAC / SHA-2)                                                |            |

3. Risk rationale: Explain why using a shared static key (the current Perfect Forward Secret model) is a critical risk compared to an ephemeral key.

## Activity 2. Authentication Systems

NexusLifePharma is launching a mobile app for pharmacists to validate prescriptions. You must choose between two mechanisms to manage API sessions: JWT tokens (JSON Web Tokens) or Server Identifier-based sessions (traditional cookies). Compare both mechanisms focused on security, using the following table.

![Image](artifacts/image_000002_a9fcee9410a30933ac50081f039464d4d7ac58b4ebb1fd0cf1b790663d6a056f.png)

UOC

uoc.edu

| Criteria      | JWT tokens   | Sessions (Cookies)   |
|---------------|--------------|----------------------|
| State storage |              |                      |
| Main risk     |              |                      |
| Revocation    |              |                      |

and explain your choice for a high-traffic environment.

## Activity 3. Data Protection at Rest and Compliance

The  audit  reveals  that  customers'  Social  Security  numbers  and  IBANs  are  stored  in  the database using a simple hash (SHA-256). This situation reminds us of the Energia XII recent news story:

https://www.lavanguardia.com/economia/20260111/11428973/energia-xxi-notificaciberataque-compromete-datos-contratos-dnis-clientes.html

As  you  can  see  in  PR3,  applying  only  this  measure  is  not  enough  to  have  a  secure environment. Explain why this measure is safe enough against a data exfiltration attack (like the one that occurred at Energía XXI) and propose an architecture that combines both salting and an HSM (Hardware Security Module).

## Personal reflection

Finally,  to  achieve  the  highest  grade,  we  ask  you  to  conclude  your  solution  with  a  brief personal reflection on what you learned during the activity and any personal insights you may have UOC

![Image](artifacts/image_000003_ea12004327c131fe98760e493027a1b409269de254070915cb931e241ab2323c.png)

## Assessment criteria, assignment format and deadline

This challenge serves as a summary of all the work completed and is the sole evidence used to  assess  your  learning  process throughout the course.  Therefore,  it  is crucial  to  dedicate sufficient time to completing all proposed activities and to include any relevant evidence that properly demonstrates your progress.

The evaluation of this activity will follow the criteria outlined in the rubric. The successful completion of challenge activities will account for 90% of the total grade, while the remaining 10% will be based on assignment format, proper use of references, and the inclusion of a final reflection.

It  is  essential  to  cite  all  sources  of  information  and  links  used  in  each  activity,  providing additional details beyond just a list of URLs (e.g., include the resource title, access date, etc.). For images, the source must be indicated at the bottom of the image. If you are the author, simply note it as "Own creation."

Any text or figure included in the solution must be referenced unless it is the student's original idea. Therefore, anything that is not the student's original idea and is not referenced may be considered plagiarism or generated by artificial intelligence.

For  activities  that  require  running  programs  and  commands,  it  is  essential  to justify  the parameters used and their values . Including screenshots to demonstrate the completion of practical  tasks  is  important,  but  all  screenshots  must  be  annotated  and clearly  show  the student's  UOC  username (e.g.,  in  the  terminal  prompt).  Submitting  screenshots  without comments or including an excessive number of unnecessary images will be penalized.

Additionally, pay attention to the format and clarity of your writing. The assignment should not exceed 10 to 12 pages ,  including a cover page, and must use a size 12 font. Do not include the task instructions in your submission.

Finally, conclude your assignment with a brief personal reflection on what you learned during the process and any additional insights or thoughts you may have.

This  activity  must  be  submitted  through  the  appropriate  section  in  the  virtual classroom , where the deadline will also be indicated. You should upload a single PDF file containing the entire assignment.