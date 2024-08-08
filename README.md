# Phishing-Analysis-and-Email-Forensics-Lab

## Objective

This project aims to provide a comprehensive guide of analyzing phishing emails through a series of practical exercises and detailed explanations when going through the Tryhackme Phishing module. I will apply these skills by utilizing industry-standard tools to identify, analyze, defend against phishing emails by completing the objectives outlined in the module and doing further research. I will also be including incident response steps. 


### Skills Learned

- Phishing Analysis and Email Forensics
- Decoded Email Headers and Bodies for Phishing Detection
- Gained expertise in defending against phishing attacks
- Leveraged a variety of investigative tools to collect data on phishing emails
- Email Structure and Phishing Techniques
- Process of how an email travels from sender to recipient


### Tools Used


- Tryhackme
- AnyRun
- Cyber Chef
- Azure Message Header Analyzer
- Based64 Guru
- DMARC Domain Checker
  

## Analyzing Phishing Emails

1. Investigated emails by breaking it down by examining the from, subject, date, to, return path, envelope to, delivery date, received, content type, and the message body.

2. On a VM within the Tryhackme lab the objective was to deconstruct the based64 email 2 txt file to reveal the text in the PDF that you see below.

 <img width="465" alt="based 64 notepad" src="https://github.com/user-attachments/assets/f8b9adcb-0de4-4057-a573-e32130874cd9">

  
3. I then used the Base64 Guru tool to decode the text by copying and pasting it into the tool, which revealed the original content in the preview section.

   <img width="644" alt="converting based 64 into a PDF to find text within PDF" src="https://github.com/user-attachments/assets/fe8577fa-6b1e-43b2-8840-c696826bde1f">

4. My next task was to complete four objectives: identify the trusted entity the third text file email was impersonating, find the sender's email address, determine the subject line, and defang the URL as the final step. I entered the commands below in the VM terminal to retrieve and analyze the email.
  
  <img width="457" alt="image" src="https://github.com/user-attachments/assets/306717be-f44f-4218-87d2-6c57437d6dd1">


5. After running the final line of code, the email populated as shown below.

   
   <img width="655" alt="image" src="https://github.com/user-attachments/assets/fa1e9acc-4796-46d6-bac7-2e45e9fd9c02">


6. After running the code, it revealed the email masquerading as Home Depot, along with the sender's email address and the subject line. The final task was to defang the URL to make it unclickable.

 *Note that the from section it states it came from support@teckbe[.]com
   
   *You will also notice random text at the bottom stating "Or you may write to Space Tree technology" and provides a PO box- This is a red flag as it has nothing to do with Home Depot.
   
   *My last observation is the small amount of code towards the bottom left of the email. A reputable company would most not likely send out an email with exposed code.

7. I went into the email 3 txt file and copied the information.

   <img width="496" alt="image" src="https://github.com/user-attachments/assets/efd3382d-4619-47de-af3e-2020f946ad22">

8. Next, I configured the Cyber Chef application to defang the URL. I then pasted the copied information from the third email text file, which resulted in a defanged URL.

   <img width="323" alt="image" src="https://github.com/user-attachments/assets/ee3ae680-0792-4fc1-8107-6b34c4eed121">

   ## Phishing Scenario 1

  Tryhackme Objective 1: Identify the brand this email was tailored to impersonate - I navigated to the terminal and opened the EML file and identified that the email was posing as Netflix. Furthermore, I copied and pasted the body of the email into Azure Message Analyzer and identified that Netflix was the brand as well. I will show the eml file, the Analyzer results, Terminal commands, and the email itself below.

<img width="465" alt="image" src="https://github.com/user-attachments/assets/a13699f7-531c-4dd5-887f-7c4c409ccce0">



<img width="464" alt="image" src="https://github.com/user-attachments/assets/b0b7aec1-d4e4-4d61-9bc4-fc62ba17c50b">


I copied the eml file text below.







   <img width="464" alt="image" src="https://github.com/user-attachments/assets/40b6e20c-2654-4b50-b96c-a5b690f6bb5a">

   

   I pasted the info into the Azure Message Header Analyzer and the results are shown below. 

   <img width="596" alt="image" src="https://github.com/user-attachments/assets/08f9de3a-0331-4423-9c16-a5453092845b">

  Tryhackme Objective 2: Identify the from in the email address - I utilized the Azure Message Header Analyzer tool and identifed where the phish came from and is underlined in the screenshot below.

  <img width="709" alt="image" src="https://github.com/user-attachments/assets/49a25c01-c60b-49eb-8cb6-72539136041b">

 Tryhackme Objective 3: Identify the original IP address and defang it - Utilized Cyber Chef and pasted in the body of the email and defanged the email. The results are highlighted in the screenshot below.

  <img width="739" alt="image" src="https://github.com/user-attachments/assets/7ead413e-eca3-4e57-8f35-d7187252fa31">

  Tryhackme Objective 4: From the information gathered, identify the domain of interest and defang it - I utilized Cyber Chef to analyze the email body and successfully retrieved the domain of interest, which is underlined in the screenshot.

  <img width="734" alt="image" src="https://github.com/user-attachments/assets/6ede89e2-7473-496f-827f-195ca779fd15">

  Tryhackme Objective 5: Identify the shortened URL and defang it - Went back into the original email via the terminal. Right clicked and copied the link location.

  <img width="466" alt="image" src="https://github.com/user-attachments/assets/4f596c39-e066-4c08-8f3b-8b8c9e9f0150">

  Then I opened Cyber Chef and pasted the the URL. See below as it has been defanged.

  <img width="917" alt="image" src="https://github.com/user-attachments/assets/a62b249a-df7a-4855-a711-c2ff10fffd12">


  
## Phishing Scenario 2

Tryhackme Objective 1- Identifed what Anyrun classifies this email as (link was given on the page) - It is Identified as suspicious activity.

<img width="918" alt="image" src="https://github.com/user-attachments/assets/c627202e-df58-4d1b-8077-347035a73791">

Tryhackme Objective 2- Identify the name of the PDF- Identified it as Payment-updateid.PDF

<img width="916" alt="image" src="https://github.com/user-attachments/assets/adb44f67-f22e-4ba9-ba96-ee12d356e90a">

Tryhackme Objective 3- Identify what the SHA 256 hash is for the PDF - The SHA 256 hash is in the screenshot underlined below.

<img width="698" alt="image" src="https://github.com/user-attachments/assets/0a5d1ca3-40b6-45ac-b9d5-aa7f7caea015">

Tryhackme Objective 4- Identify 2 IP address that are classified as malicious and defang them - Clicked on the Text report option.

<img width="921" alt="image" src="https://github.com/user-attachments/assets/5e49887d-bac7-4100-ac34-61b5047f89b1">

Within the text report I was able to Identify both malicious IP addresses.

<img width="869" alt="image" src="https://github.com/user-attachments/assets/19e772a1-5abf-481e-8f17-a5a150ad3025">

<img width="860" alt="image" src="https://github.com/user-attachments/assets/9f063ad6-2ebb-465c-908e-547eaffb1807">

Then I navigated to Cyber Chef to defang both IP addresses.

<img width="698" alt="image" src="https://github.com/user-attachments/assets/41959abd-a503-48c9-892f-e731c7cbf755">

Tryhackme Objective 5- Identify Windows process was flagged as "Potentially bad traffic." - Was able to navigate to the threats section and identified that the exe circled in the screenshot was classified as potentially bad traffic.


<img width="884" alt="image" src="https://github.com/user-attachments/assets/472e6a39-5766-466d-8bb7-2f72b9be888a">


## Defending Against Phising Emails

SPF (Sender Policy Framework): 
Used to authenticate the sender - Published list of servers that are authorized to send mail on behalf of a domain.

IP4: Specifies the IP addresses allowed to send emails on behalf of your domain.
Domain: Specifies which domain is authorized to receive emails.
Modifiers:

-all: Rejects all unauthorized emails.

~all: (Softfail): Accepts unauthorized emails but marks them as suspicious.

+all: Allows any server to send emails from your domain (not recommended).

Source: https://dmarcian.com/create-spf-record/

DKIM (DomainKeys Identified Mail): 
Is an email authentication method that allows the receiver to verify that an email was sent by the domain it claims to be from and that it hasn't been altered during transit. DKIM works by using cryptographic signatures, which are added to the email headers. One of the large benefits is this can survive email forwarding.

Within the excercise in the tryhackme module it breaks a DKIM record as shown below.

v=DKIM1 Version of the DKIM record.

k=rsa This is the key type. RSA is an encription algoritym

p= This is the public key that will be matched with the private key

<img width="890" alt="image" src="https://github.com/user-attachments/assets/d8ce3017-ca61-4eb1-8618-aa8e0b10d101">




DMARC (Domain-based Message Authentication, Reporting, and Conformance):
Is an email authentication protocol that builds on existing mechanisms like SPF (Sender Policy Framework) and DKIM (DomainKeys Identified Mail) to provide a way for domain owners to protect their domain from unauthorized use, commonly known as email spoofing. DMARC enables domain owners to specify how email receivers should handle messages that fail authentication checks, and it also provides a way to receive reports on the outcome of these checks.

Within the excercise in the Tryhackme module it breaks down a DMARC record as shown below.

v=DMARC1 Must be in all caps

p=quarantine If a check fails, then an email will be sent to the spam folder

rua=mailto:postmaster@webite[.]com Aggregate reports will be sent to this email address



<img width="359" alt="image" src="https://github.com/user-attachments/assets/933225d4-c519-46cb-a3e0-a818ddff969b">


  
  *You can utilize the Domain health checkher by navigating to this link and then entering the domain https://dmarcian.com/domain-checker/

 
  
  <img width="913" alt="image" src="https://github.com/user-attachments/assets/f9c65320-97b3-4c4c-8aec-f4a18ffdf7ef">








S/MIME (Secure/Multipurpose Internet Mail Extensions):
Is a widely-used standard for securing email communication by providing encryption and digital signatures. It ensures the confidentiality, integrity, and authenticity of email messages.

Encription: Encrypts the content of an email, ensuring that only the intended recipient, who possesses the correct private key, can decrypt and read the message.

Digital Signatures: Verifies the identity of the sender of an email

Source: https://learn.microsoft.com/en-us/exchange/security-and-compliance/smime-exo/smime-exo


Educating Users Within Your organization:

The Cybersecurity team plays a crucial role in safeguarding an organization's digital assets by proactively identifying and mitigating potential threats. One essential strategy to employ is launching test phishing campaigns using tools like KnowBe4. These simulations are vital for educating users about phishing techniques, helping them recognize and avoid malicious emails. By fostering awareness and training employees to be the first line of defense, the Cybersecurity team significantly reduces the risk of successful phishing attacks, thereby strengthening the organization's overall security posture.




  
















  

  



  



   


   









   ### Lessons Learned

   - I investigated the emails by analyzing various components, including the sender, subject, date, recipient, return path, envelope recipient, delivery date, received headers, content type, domain keys, and the message body.
   - Utilized a multitude of tools to retrieve important data to analyze the malicious emails.
   - Analyzed defensive protocols to defend against phishing
   - Credentials are harvested by malicious actors when someone clicks on a link and enters their login information.
   - Emails from "Netflix" or other well known companies can be spoofed very easily if the email isn't looked over. Such as the sender, spelling, ect.
   - Many spoofed phishing emails appear to be from well-known organizations and request information you have already provided, such as credit card details or your social security number.
   - Phishing emails often contain numerous grammatical errors and frequently lead to multiple redirections to various sites when clicking on a phishing link.
 









