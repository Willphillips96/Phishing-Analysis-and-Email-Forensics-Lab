# Phishing-Analysis-and-Email-Forensics-Lab

## Objective

This project aims to provide a comprehensive guide of analyzing phishing emails through a series of practical exercises and detailed explanations when going through the gohackme Phishing module. After the simulated excercises I will apply these skills with real Phishing emails at the end of the project. 

### Skills Learned

- Phishing Analysis and Email Forensics
- Decoding Email Headers and Bodies for Phishing Detection
- Email Structure and Phishing Techniques
- Process of how an email travels from sender to recipient


### Tools Used


- Tryhackme
- Based Guru
- Cyber Chef
  

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


   









   ### Lessons Learned

   - investigated emails by breaking it down by examining the from, subject, date, to, return path, envelope to, delivery date, received, content type, domain keys, and the message body.
 






drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
