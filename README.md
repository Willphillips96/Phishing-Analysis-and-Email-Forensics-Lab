# Phishing-Analysis-and-Email-Forensics-Lab

## Objective

(THIS LAB IS CURRENTLY IN PROGRESS) This project aims to provide a comprehensive guide of analyzing phishing emails through a series of practical exercises and detailed explanations when going through the gohackme Phishing module. I will apply these skills by utilizing industry-standard tools to analyze phishing emails, completing the objectives outlined in the module.

### Skills Learned

- Phishing Analysis and Email Forensics
- Decoded Email Headers and Bodies for Phishing Detection
- Leveraged a variety of investigative tools to collect data on phishing emails
- Email Structure and Phishing Techniques
- Process of how an email travels from sender to recipient


### Tools Used


- Tryhackme
- Based Guru
- Cyber Chef
- Azure Message Header Analyzer
  

## Steps

1. Investigated emails by breaking it down by examining the from, subject, date, to, return path, envelope to, delivery date, received, content type, domain keys, and the message body

2. On a VM within the Tryhackme lab the objective was to deconstruct the based64 email 2 txt file to reveal the text in the PDF that you see below.

 <img width="465" alt="based 64 notepad" src="https://github.com/user-attachments/assets/f8b9adcb-0de4-4057-a573-e32130874cd9">
  
3. I then used the Base64 Guru tool to decode the text by copying and pasting it into the tool, which revealed the original content in the preview section.

   <img width="644" alt="converting based 64 into a PDF to find text within PDF" src="https://github.com/user-attachments/assets/fe8577fa-6b1e-43b2-8840-c696826bde1f">

4. My next task was to complete four objectives: identify the trusted entity the third text file email was impersonating, find the sender's email address, determine the subject line, and defang the URL as the final step. I entered the commands below in the VM terminal to retrieve and analyze the email
  
  <img width="457" alt="image" src="https://github.com/user-attachments/assets/306717be-f44f-4218-87d2-6c57437d6dd1">


5. After executing the last line of code the email populated as you can see below.

   <img width="439" alt="image" src="https://github.com/user-attachments/assets/9277a4c3-388e-432b-a456-3b527e39cb9c">

6. After running the code, it revealed the email masquerading as Home Depot, along with the sender's email address and the subject line. The final task was to defang the URL to make it unclickable.

7. I went into the email 3 txt file and copied the information.

   <img width="496" alt="image" src="https://github.com/user-attachments/assets/efd3382d-4619-47de-af3e-2020f946ad22">

8. Next, I configured the Cyber Chef application to defang the URL. I then pasted the copied information from the third email text file, which resulted in a defanged URL.

   <img width="323" alt="image" src="https://github.com/user-attachments/assets/ee3ae680-0792-4fc1-8107-6b34c4eed121">

   ## Remediation of Phishing Emails

   Objective 1: Identify the brand this email was tailored to impersonate - After copying and pasting the body of the email into Azure Message Analyzer I identified that "Netflix" was the brand. I will show the txt file and then the Analyzer with the info below.

   <img width="464" alt="image" src="https://github.com/user-attachments/assets/40b6e20c-2654-4b50-b96c-a5b690f6bb5a">

   I input the results into the analyzer and the results are shown below.

   <img width="596" alt="image" src="https://github.com/user-attachments/assets/08f9de3a-0331-4423-9c16-a5453092845b">

   Objective 2: Identify the from in the email address - I utilized the Azure Message Header Analyzer tool and identifed where the phish came from and is underlined in the screenshot below.

  <img width="709" alt="image" src="https://github.com/user-attachments/assets/49a25c01-c60b-49eb-8cb6-72539136041b">

  Objective 3: Identify the original IP address and defang it - Utilized Cyber Chef and pasted in the body of the email and defanged the email. The results are highlighted in the screenshot below.

  <img width="739" alt="image" src="https://github.com/user-attachments/assets/7ead413e-eca3-4e57-8f35-d7187252fa31">

  Objective 4: From the information gathered, identify the domain of interest and defang it - I utilized Cyber Chef to analyze the email body and successfully retrieved the domain of interest, which is underlined in the screenshot.

  <img width="734" alt="image" src="https://github.com/user-attachments/assets/6ede89e2-7473-496f-827f-195ca779fd15">

  Objective 5: Identify the shortened URL and defang it - 


  

  



  



   


   









   ### Lessons Learned

   - I investigated the emails by analyzing various components, including the sender, subject, date, recipient, return path, envelope recipient, delivery date, received headers, content type, domain keys, and the message body.
   - Phishing emails often contain numerous grammatical errors and frequently lead to multiple redirections to various sites when clicking on a phishing link.
   - Credentials are harvested by malicious actors when someone clicks on a link and enters their login information.
   - Emails from "Netflix" or other well known companies can be spoofed very easily if the email isn't looked over. Such as the sender, spelling, ect.
   - Many spoofed phishing emails appear to be from well-known organizations and request information you have already provided, such as credit card details or your social security number.
   - A red flag is an email that pressures you to urgently provide login credentials or personal information, often with a threat of negative consequences.
 








Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
