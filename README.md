![shield](https://user-images.githubusercontent.com/21206324/70219631-71580e80-1745-11ea-8c0d-05d0706891a5.PNG)


# About AREUSE 
**AREUSE** is a Swiss startup, with 3 co-founders, specialized in the human resources sector and information technology. 
**AREUSE** aims to provide unique, simplified and convenient job offering and seeking process. Currently, **AREUSE** is providing professional candidates (Job Seekers) to Trust Square in Zurich, IT startup cluster in the area of Blockchain and AI. **AREUSE** agency will typically keep a file for each employee noting their skills and work history. This helps Trust square to match job seekers experience and skills to their requirements. 

![the Big Picture](https://github.com/DigiBP/DigiBP-AREUSE/blob/master/src/modelling/areuseGeneral.PNG)


 # Who are we?
We are trusted service providers offering two main types of services. One is directed at the job seeker and the other to an employer looking to hire new employees. **AREUSE** has a continuous reputation of matching candidates’ knowledge, proficiency, capability and qualification with specific job requirements in the field of Block chain and AI. We specialize in identifying talent in the labor market and making it available via Trust square to organizations that require skilled and talented people for various positions. **AREUSE** works as an intermediary in the hiring process by screening the candidate to find a suitable place of employment, where the candidate’s expertise and competence would benefit the company or position in question.

![Webp net-resizeimage](https://user-images.githubusercontent.com/55685771/68245892-0d440c80-0018-11ea-94b8-8da98302d896.png)

![Webp net-](https://user-images.githubusercontent.com/55685771/68246986-336aac00-001a-11ea-919b-863a1663bc16.png)


# Objective
The main objectives of **AREUSE** is to match between Blockchain and AI job offers in Zurich and experienced talented programmers who are looking to dive into cutting edge technologies in a more convenient and effective way, where the primary screening of candidates is done by using the latest artificial Intelligence services. Our fully automated process matches candidates with job offers  through a conversation made between a candidate and our chatbox, along with an automated analysis of the candidate’s CV whom later is offered tests that matches the job opportunities and suits the candidate. 

One of our hallmarks is the successful placement of suitable job candidates in the area of Blockchain and AI.


# Our Mission 
Make the difference for our client and the candidates. We place both in the center of everything we do. **AREUSE** is fully committed to their success and mutual benefit in every aspects of their challenge. We transform recruitment process with our leading-edge digital technology and process knowledge. 

## Benefit for Employer
The employer signs up for **AREUSE** when a position becomes available in their organization. One of the primary benefits for the employer is that the company does not have to spend time in screening CV’s, candidate communications including follow ups and launch job availability campaigns. This saves time, money and resources for the employer. It also helps HR Team to deal with more important things. When the candidates proposed by AREUSE and selected by client, they are expected to possess relevant skills and experience, which will shorten the training period for the employer.

## Benefit for Employee
**AREUSE** reduces stress for the candidates by avoiding tedious and time consuming recruitment process. **AREUSE** improves candidate’s experience and better job satisfaction by getting appropriate job and matching his/her skill set. More over it does not cost anything for the employees.


# Our Vision 
Our vision is to provide our employer clients and candidates with world class recruitment service focused on high quality, trust, efficiency and cost-effective. We aim to empower our job seekers to find the job they always dream of, develop relationships, and overall business together.

# Our Service Model

## As-Is process: 

The employee recruitment process of our company has two models:
###### 1. The steps in Job opening process model:
* Jobs received from Trust square
* Listing jobs 
* Placing  job advertisements for job seekers

###### 2. The steps in Job recruitment process model:
* Receiving applications from candidates
* Screening the candidate through phone call and evaluation of CV, motivation letter
* Candidate selection
* Sending candidate profile to Trust square 
* Updating Data base with candidate’s profile



# Current Situation
![Current Manual Process bpmn 4](https://user-images.githubusercontent.com/55553886/69800084-d0150980-11d4-11ea-9788-cd8a37ddce6d.jpeg)

# To-Be Process
AREUSE to improve the job seeker experience and to have Job search more efficient, an AI assistance.i.e,chat bot communicate with the Candidate by text ,answers common questions and automates much of the communication through Integromat to extract text tags and email address of the Candidate to request  CV. Uploaded Candidate 's CV integromates with Rezscore for scoring based on their algorithm with a grading from A to F. Candidates with higher threshold are sent with the most appropriate jobs from our AREUSE database (google sheets) and sends all the relevant tests to evaluate the candidate technical and programming skills outlined in the resume with a timelapse of 24hours .The qualified candidates profile is sent to our client  for assessment and simultaneously request  for feedback from both the Client and Candidate and saved to our Areuse database (google sheets).

###### The steps involved in the recruitment process:
* Chat received from the Chatbot
* Interpretation of the email address and tagged text.
* Request to upload CV.
* Scoring of the CV with various grades ranging from A to F (If the Grade is A/B-Selected,C-Send to Review,D/E/F -Not Selected)
* Matching CV Score with the Appropriate job from the database.
* Relevant Tests are sent to evaluate the Candidate technical and programming skills.
* Evaluation of the Tests (If Passed-Selected ,If Fails- Not selected)
* Selected Candidate profile sent to Client.
* Request for Feedback from both Candidate and Client.
* Save the Feedback to the Database.

# To-Be Situation
![AreuseTobe](https://user-images.githubusercontent.com/21206324/69092376-8433c900-0a4c-11ea-89e6-c8f60c04adf7.png)

| | | |
|-|-|-|
| __Element__  | Start Event  |
| __Name__  | chat received  |
| __General description__  | a message event that starts the process when receiving a chat history between our AI and a job seeker  |
| __Input__  | a chat history from dialogflow  |
| __Output__  | tagged texts that contain candidate email and information from chat  |	


| | | |
|-|-|-|
| __Element__  | Script task  |
| __Name__  | Extract Email |
| __General description__  | a script task is an automated activity interprets the email address from the chat received and creates a respective task so the process continues.  |
| __Input__  | tagged text from the message event  |
| __Output__  | email variable that contains the business key (candidate email)  |	


| | | |
|-|-|-|
| __Element__  | Service Task |
| __Name__  | Extract Tags from chat |
| __General description__  | a service task takes the information and perform some technical aspect of the process flow i.e, extract tags from the chat and trigger some action and integrate with another task |
| __Input__  | tagged text from the message event |
| __Output__  | variables with their respective values extracted from tags|	



| | | |
|-|-|-|
| __Element__  | Send Task  |
| __Name__  | Send email to upload CV |
| __General description__  | a send task sends an email to the candidate asking him/her to reply with a CV|
| __Input__  | Business Key (email address) |
| __Output__  | confirmation of email sent  |	


| | | |
|-|-|-|
| __Element__  | Message intermediate throw event|
| __Name__  | CV received |
| __General description__  | a message intermediate throw event task waits for an email to arrive from the candidate and intiate the CV screening of the processflow |
| __Input__  | signal from Integromat that the candidate sent the CV |
| __Output__  | permit the flow to proceed |	


| | | |
|-|-|-|
| __Element__  | Service Task|
| __Name__  | Get CV score |
| __General description__  | a service task triggers a request to a workflow in Integromat which sends the cv to RizScore and get a scoring based on their algorithm|
| __Input__  | CV file in pdf or word |
| __Output__  | a CV score which varies from A to F|	


| | | |
|-|-|-|
| __Element__  | Manual Task |
| __Name__  | Review Cv |
| __General description__  | a Manual task is a non automated task where the activity is performed by the user reaching to the client and expert advisors to check if CV needs translation/convert  its format to either give -1/+1|
| __Input__  | receives an CV Score with C Score |
| __Output__  | an adapted CV score of either A/B or D/F|	


| | | |
|-|-|-|
| __Element__  | Script Task |
| __Name__  | Save Candidate lnformation |
| __General description__  | a script task saves the candidate information to our AREUSE database and then trigger the respective task|
| __Input__  | data about the candidate information with all the outlined requirements |
| __Output__  | a signal that data is now saved to our database (google sheets) |	


| | | |
|-|-|-|
| __Element__  |Script Task |
| __Name__  | Find most appropriate Job information |
| __General description__  | a script task finds the most appropriate job from our AREUSE data store references |
| __Input__  | updated google sheets with candidate information |
| __Output__  | lists out the appropriate jobs |


| | | |
|-|-|-|
| __Element__  |Send Task |
| __Name__  |Send attached tests |
| __General description__  | a send task will send a message to the candidate which includes the relevant tests to evaluate the candidate technical and programming skills outlined in the resume |
| __Input__  | Matches candidate information with job lists  |
| __Output__  | relevant tests sent |



| | | |
|-|-|-|
| __Element__  | Timer Boundary Event |
| __Name__  | Wait for test result|
| __General description__  | a Timer boundary event waits for 24hours for the candidate response |




| | | |
|-|-|-|
| __Element__  | Message End Event |
| __Name__  | send rejection |
| __General description__  | a message end event sends a rejection email if the candidate fails to meet the appropriate score |



| | | |
|-|-|-|
| __Element__  | Send Task |
| __Name__  | Inform candidate |
| __General description__  |  a send task sends a message to the candidate to inform the test result |
| __Input__  | Test result received |
| __Output__  | Result information sent |


| | | |
|-|-|-|
| __Element__  | Send Task |
| __Name__  | Send candidate profile |
| __General description__  |  a send task sends a message of the candidate's profile to the client |
| __Input__  | Test result received |
| __Output__  |  Candidate profile sent to client |


| | | |
|-|-|-|
| __Element__  | Message Intermediate Catch event |
| __Name__  | Wait for feedback of Candidate|
| __General description__  |  a message intermediate catch event waits for the feedback from our client |
| __Input__  | Request the candidate for feedback |
| __Output__  | Receives feedback from the candidate |


| | | |
|-|-|-|
| __Element__  | Task |
| __Name__  | Save client feedback |
| __General description__  |  saves the feedback to our AREUSE database |
| __Input__  | Gets the Trust square clients feedback |
| __Output__  | stores to database  |


| | | |
|-|-|-|
| __Element__  | End Event|
| __Name__  | End |
| __General description__  |  a end event ends the process after receiving the client's feedback and saving the candidate profile to the AREUSE database |

