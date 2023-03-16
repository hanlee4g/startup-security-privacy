# The Privacy and Security Guide for Tech Startups
#### Authors: [Hanjune Lee](https://www.linkedin.com/in/hanjunelee/), [Abenezer Tamene](https://www.linkedin.com/in/abenezer-tamene-649500182/), [Dennis Wu](https://www.linkedin.com/in/dennis-y-wu-501b911a3/)
The following document outlines the critical steps that early-stage technology-focused startups need to follow to (1) safeguard against external security threats and (2) ensure legal compliance & avoid fines. We have stuctured this guide into 4 distinct sections. The presentation version of this guide can be viewed [here](https://docs.google.com/presentation/d/14-oCW4beoxqBe_H7dyoYf4jDbFymFvzkgbXTl1HbHSg/edit?usp=sharing).
### Table of contents:
1. Preventing & Mitigating Data Breaches
2. Securing your Infrastructure
3. Writing an Effective Privacy Policy
4. Educating your Employees


## (1) Preventing & Mitigating Data Breaches

### Why should you care?
Data breaches can cost your company a ton of money.
* **IBM 2022 Data Breach Report**: "*Avg. cost of a data breach in 2022 is <span style="color:red">**4.35M**</span>."*
* **NationWide & UK Government**: "*<span style="color:red">**3 out of every 5**</span>. small companies have faced at least one data breach in the last two years."*
* **IBM 2022 Data Breach Report**: "*<span style="color:red">**60%**</span> of data breaches led to an increased price pass on to customers."*

Data breaches are very common among small-to-midsize businesses. The following security and privacy measures  for data breach prevention are also for **cost mitigation.**

The graph below depicts the different types of data breaches and their frequencies + average costs. It's clear that all are costly.
> ![Avg. Cost of Common Data Breaches (Measured in USD millions)](https://i.imgur.com/SIAC0eq.png)

There are 3 main factors that cause data breaches
* User-Related
    * Social engineering, phishing etc.
* Infrastructure-Related
    * Cloud misconfiguration, vulnerable third-party tools etc.
* Employee-Related
    * Business email compromise, malicious insider accidental data loss etc.

We can prevent and mitigate data breaches through 4 approaches: the user persepctive, the incident response perspective, the infrastructure perspective, and the employee perspective. The first two will be covered in this section, while the latter two will be covered in their own dedicated sections.

### How to Prevent & Mitigate Data Breaches (User Perspective)
This section covers tips for securing user data by protecting their accounts that you can implement into your product or service. We will cover:
1. Multi-factor Authentication (MFA) ([Google's Identity API](https://developers.google.com/identity/oauth2/web/guides/overview))
2. Good Password Policy

#### Multi-factor Authentication
MFA was seen as one of the most convenient way to protect user accounts. While passwords failed to protect malicious attacks, MFA provides an extra layer of verification to ensure the identity of the person who try to log in. MFA can be verified by obtaining information from an extra source like text messages, other devices or email.

#### Password Policy
* Password Blocking
    * Do not allow users to create passwords like: `password`, `123456`, `iloveyou` etc.
    * [Password blocking list](https://github.com/danielmiessler/SecLists/blob/master/Passwords/Common-Credentials/100k-most-used-passwords-NCSC.txt)
* Guessability over Complexity
    * Password complexity do not always transfer to it security level, but gussability does!!
    * Design your password meter with guessability using the [Password Guessability Service](https://pgs.ece.cmu.edu/) (PGS)

* Prevent Using Character-based Composition Policy
    * According to this [research](https://www.usenix.org/conference/soups2022/presentation/lee), limiting certain type of symbols (upper letter, special symbols) in a password does make passwords easier to guess.

    

### How to Prevent & Mitigate Data Breaches (Incident Response)
 What is an **incident response (IR)** plan?
 
 *A step-by-step playbook for a company to response and handle data breaches. Including fixing vulnerabilities, public response etc.*



| IR completeness    |  No IR plan testing or IR team    | Testing IR plan regularly | Testing IR plan regularly + IR team formation |
| --- | ---- | -------- | -------- |
| Data breach avg. cost    | <span style="color:red">**5.92M**</span> | 4.47M     | <span style="color:green">**3.26M**</span>     |

> [name=Our Suggestion] Having an IR team can be expensive, but try to come up with and test an IR plan at minimum.


#### You should aim to include guidelines for the following areas in your IR plan (at a minimum):
* **Stop Additional Data Loss**
    * Put down affected servers, websites or any related services.
* **Consult with Legal Council**
    * Contact your lawyer for further legal actions.
* **Fix Vulnerability**
    * Check your code, website, third-party tools etc.
* **Notify Appropriate Parties**
    * Notify your service providers, related third-party partners.
* **Send out Data Breach Notification**
    * How did it happened?
    * Who was affected?
    * Necessary measures.
* **Conserve Evidence**
    * Prepare for potential lawsuit


### If your company handles sensitive data, you need a Zero Trust Framework

> [name=Our suggestion] Treat your data differently, put sensitive data in a more secured environment like zero trust framework.


A zero trust framework essentially realized the idea of **"not trusting anyone"**.

For example, if Jane works closely with the sensitive data, a traditional security framework might put Jane's account on a white list, and everyone on a white list can get access to this special database. However, what if Jane's account was compromised? (we see that how common business email compromise can cause a data breach). 

So zero trust framework basically constantly verify users and devices regardless of their position or role. In zero trust framework, Jane might have to send her requst to the policy admin every 2 hours to maintain the access to sensitive data.


![](https://i.imgur.com/gIEjA54.png)

The graph above shows the impat of zero trust frameworks on data breaches (in millions).


## (2) Securing your Infrastructure
### Why should you care?
Your infrastructure is at the base of your product or service; securing it is a top priority as external threats in this area can cause existential risks. In this section, we will cover how to choose between public and private databases, what to do if you have a custom backend, penetration testing, and XDR tools.

### Should you use Public or Private infrastructure?

Tech start-up companies often have to make decisions on whether they should set up their own cloud infrastructure or use existing, publicly-documented services like Microsoft Azure, Amazon AWS, or Google Cloud. Since the main focuses of start-ups are generally in product development, marketing, and financing, and not in security, **we recommended that companies make use of existing services**.

According to Servermania [Servermania](https://www.servermania.com/kb/articles/how-much-does-a-server-cost-for-a-small-business/), the average cost of server rent is $40/month per 160GB of storage. For the same storage, Google firebase costs just over $4. In addition to server storage, companies also have to think about bandwidth and other factors that come with setting up infrasture. Moreover, as the user base increases, scaling services provided by Firebase or other well-known cloud service providers is much easier as all companies have to do is pay more and add services. 

In addition to the **scalability**, public infrastructures provide the flexibility of adding or removing services based on need. Companies can add services like in-app messaging, the ability to push updates, app analytics, etc. Some of the possible features that are included in a well-established cloud service provider are listed below.

![image alt](https://imgur.com/CaPzsjm.png)

> [name=Our Suggestion] Set up cloud services for your company on well-tested publicly documented cloud service providers.




### If your company does use a custom backend infrastructure, we recommend...

* Having a security expert on the team, if feasible, as as he/she will help design the product with security and scalability in mind. 
* Doing regular penetration testing on backend and frontend

### How to do Penetration Testing
Penetration testing is an authorized simulated cyberattack on a computer system, performed to evaluate the security of the system.

We recommend the following tools for penetration testing:

* **Invicti**: a web application vulnerability scanner. It's scalable and can be integrated to workflows. View this [introductory video](https://www.youtube.com/watch?v=osd4a2h1hFY&ab_channel=InvictiSecurity) for more information.
* **SQLMap**: used to find and exploit SQL injection flaws – i.e., when user input can alter the execution of the SQL query. Works with different kinds of Databases like MySQL, Oracle, Microsoft SQL Server. View [documentation](https://sqlmap.org/) and an [introductory video](https://www.youtube.com/watch?v=nVj8MUKkzQk) for more information.


### If you your company handles sensitive information, use an XDR Tool
XDR (Use Extend Detection and Response) tools are used to monitor threats. If your company handles sensitive information (medical, financial, etc) it's important to have a tool to track threats and network activties.

XDR Collects and automatically correlates data across multiple security layers, allowing for faster detection of threats and improved investigation/response times. In other words, XDR is a tool to **manage or track activities in your network.**

If you need more reasons to use an XDR, the financial impacts are substantial as seen in the table below:

|                            | Without XDR | Global Avg. | With XDR |
| -------------------------- | ----------- | ----------- | -------- |
| Days to Detect                          |223             |207             |   203       |
| Days to Contain            | 81          | 72          | 70       |
| Average Cost of Data Breach | 4.55M       | 4.35M       | 4.15M    |


As these tools are more involved, you should definitely do your own further research to select the best option. Our favorite is the [Palo Alto Networks Cortex XDR](https://www.paloaltonetworks.com/cortex/cortex-xdr) (pictured below).

![](https://i.imgur.com/kLcTZSm.png)



 
## (3) Writing an Effective Privacy Policy
### Why should you care?
There are substantial fines that your startup could face if found to be in violation of privacy regulations:
* <span style="color:red">**$2,500**</span> for violating CalOPPA
    * CalOPPA requires companies' websites to feature a conspicuous **privacy policy** stating exactly **what information is collected** and **with whom it is shared**; it also requires the operator of the website or online service to comply with the site’s privacy policy.
* <span style="color:red">**$43,000**</span> per child per COPPA violation
    * COPPA imposes certain requirements on operators of websites or online services **directed to children under 13 years of age**, and on operators of other websites or online services that have actual knowledge that they are collecting personal information online from a child under 13 years of age.
* <span style="color:red">**€10,000,000**</span> for violating GDPR
    * The main principles of the GDPR are that companies **must only collect data for specific, explicit, and legitimate purposes**, and that the data must be **accurate and up to date**, **not be retained for a longer period than is required**, and be processed in a way that **ensures appropriate security**.
### What goes in a Privacy Policy?
While the contents of a privacy policy should be catered towards the specific industry and business, all privacy policies should have the following content at minimum:
* What data is being collected?
* How is the data collected?
* What is the purpose of the data collection process?
* Who will have access to the data?
* How will users get access to their data?
* How will users be informed about policy changes?
* How is the data protected?

### Privacy Policy Generators
Ideally, privacy policies should be written by a lawyer. But early-stage startups often do not the have the time or the resources to go find a lawyer. As a result, a sufficient **short term solution** is to use a privacy policy generator. Our recommended **free** solutions are below:
* [Open Source Solution](https://app-privacy-policy-generator.firebaseapp.com/)
* [Shopify](https://www.shopify.com/tools/policy-generator)
* [Termsfeed](https://www.termsfeed.com/privacy-policy-generator/)
* [Termly](https://termly.io/products/tl/privacy-policy-generator/)

A screenshot of the Open Source Solution is displayed below:

![](https://i.imgur.com/CddjgcY.png)


**Always** read through the privacy policy that these websites generate to ensure accuracy.

### Additional Recommendations
When writing a policy from scratch or modifying a policy provided by a lawyer or generator, please keep in mind the following recommendations:
* If your company handles sensitive information (medical, financial, etc), please make sure to add the required information.
* Avoid terms that are vague or overly technical. If  technical terms are necessary, make sure to clearly define them.
* Make sure that the privacy policy is easily accessible by users.
* Ensure that the policy has a [good readability score](https://readabilityformulas.com/free-readability-formula-tests.php)
* Notify users about updates

## (4) Educating your Employees
### Why should you care?
Training your employees can save your company money.
* The average cost of business email compromises is <span style="color:red">**$4,890,000**</span>
* The additional cost in data breaches when remote working is a factor is <span style="color:red">**$1,000,000**</span>

### How to train your employees
There are many, many things that are important to teach your employees to minimize security and privacy risks. It is up to each company to determine what is most important given the industry, location, and other factors. As a baseline, we recommend that you co ver the following concepts at a minimum:
* Social engineering identification
* Physical security of devices
* Be careful when syncing data across devices
* Create a reliable and secure password
* Identifying suspicious links and attachments from phishing attacks.

Developing in-house content or contracting educational training companies can be resource-intensive; our recommended alternative is the use of pre-made videos. Our favorite training video is linked [here](https://www.youtube.com/watch?v=wygwHXYj_TI&ab_channel=BurgiTechnologies
).

### Evaluate your employees
After providing educational content for your employees, evaluating their retention of key facts is critical. We recommend using a brief quiz with a required minimum  score. An example quiz is listed below that is based off our previously mentioned [video](https://www.youtube.com/watch?v=wygwHXYj_TI&ab_channel=BurgiTechnologies
).



| Questions | Answers |
| --------- | ------- |
| Name 3 ways that your work computer can be infected by malware. | Clicking on malicious links in emails, Plugging in an unknown flash drive, Downloading malware masquerading as other software.|
| True or False? All websites secured by HTTPS are safe.  | False        |
| What are 4 steps to prevent phishing attacks   |Check who the sender really is, Check the email for spelling and grammar mistakes, Mouse over the link and type the company's url into your browswer, Contact your IT team if you are still unsure about the email.         |
| Why do routinely changed passwords need to change substantially? | It is very simple to try all alternative options of a password base; computer can try all options in seconds.        |
| How many unique malware threats happen per day? |390,000         |

---

## Conclusion

- [x] 1. ~~Preventing & Mitigating Data Breaches~~
- [x] 2. ~~Securing your Infrastructure~~
- [x] 3. ~~Writing an Effective Privacy Policy~~
- [x] 4. ~~Educating your Employees~~

Now that you have completed all the required steps to (1) safeguard against external security threats and (2) ensure legal compliance & avoid fines, you can grow your business, stress-free!

### References
* [Zero Trust](https://www.crowdstrike.com/cybersecurity-101/zero-trust-security/)
* [XDR Image](https://www.bing.com/images/search?view=detailV2&ccid=7Ns6JwDy&id=D0AE4FC0E1AB1B4EACF6BE115BD5765848156B33&thid=OIP.7Ns6JwDyfEqeJD9GEH8iwwHaEK&mediaurl=https%3a%2f%2fwww.paloaltonetworks.com%2fcontent%2fdam%2fpan%2fen_US%2fnorthstar%2fcortex-xdr%2f1-Hero-CloudIdentity-White-1920x1080.jpg&cdnurl=https%3a%2f%2fth.bing.com%2fth%2fid%2fR.ecdb3a2700f27c4a9e243f46107f22c3%3frik%3dM2sVSFh21VsRvg%26pid%3dImgRaw%26r%3d0&exph=1080&expw=1920&q=XDR+tool+example&simid=607995768462257067&FORM=IRPRST&ck=EE8E5053C241A03680A6B77FB1F823C9&selectedIndex=8&ajaxhist=0&ajaxserp=0)
* [CalOPPA](https://consumercal.org/about-cfc/cfc-education-foundation/california-online-privacy-protection-act-caloppa-3/)
* [COPPA](https://www.ftc.gov/business-guidance/resources/complying-coppa-frequently-asked-questions)
* [GDPR](https://gdpr-info.eu/)
* [IBM Cost of a Data Breach 2020](https://www.ibm.com/reports/data-breach)
* [Carnegie Endowment for International Peace's Timeline of Breaches](https://carnegieendowment.org/specialprojects/protectingfinancialstability/timeline)
* [Google Web Authorization](https://developers.google.com/identity/oauth2/web/guides/overview)
* [List of bad passwords](https://github.com/danielmiessler/SecLists/blob/master/Passwords/Common-Credentials/100k-most-used-passwords-NCSC.txt)
* [CMU's Password Guessability Service](https://pgs.ece.cmu.edu/)
* [How to get started with AWS](https://www.youtube.com/watch?v=ubCNZRNjhyo)
* [Intro to Invicti Penetration Testing](https://www.youtube.com/watch?v=osd4a2h1hFY&ab_channel=InvictiSecurity)
* [SQL Map Documentation](https://sqlmap.org/)
* [Fines for not having a privacy policy](https://www.termsfeed.com/blog/fines-no-privacy-policy/)
* [Text Readability Tool](https://readabilityformulas.com/free-readability-formula-tests.php)

### Acknowledgements
This guide was put together as part of Northwestern University's [COMP_SCI 396-0-5: Security and Privacy Education](https://www.mccormick.northwestern.edu/computer-science/academics/courses/descriptions/396-496-13.html) (Winter Quarter 2023). Thank you to the course's instructor, [Sruti Bhagavatula](https://users.cs.northwestern.edu/~srutib/), for providing us with vital feedback and direction.
