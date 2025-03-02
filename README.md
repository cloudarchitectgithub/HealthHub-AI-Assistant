# Implementation of AI Agent Capable of Providing Customer Support and Scheduling Medical Appointments Using OpenAI API, Functions (API Call), And Rag (Retrieval-Augmented Generation) System

<p align="center">
<img src="https://i.imgur.com/tloobwE.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
## Project Description
This project involved developing a healthcare platform using cutting-edge AI technologies to enhance the experience of doctors and patients in a medical setting. The system integrates natural language processing (NLP), image recognition, transcription, and text-to-speech capabilities. We used AWS, Microsoft Azure, Google Cloud, and OpenAI tools to implement AI services for speech-to-text, image analysis, language translation, and appointment scheduling. The platform processes medical data such as speech recordings and medical images, converting them into useful insights like transcriptions and diagnoses.

Our solution operates through a serverless architecture to scale easily and minimize cost, while ensuring data security and compliance with medical privacy regulations. Both doctors and patients can interact with the platform via an intuitive interface, and the solution leverages various cloud services for efficiency, security, and performance monitoring.

<p align="center">
<img src="https://i.imgur.com/2MeldtA.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
The solution integrates multiple cloud services and AI tools, leveraging AWS, Azure, Google Cloud, and OpenAI to provide a robust and scalable architecture.

## Project Objectives:
1. **Integration of Cloud AI Services:**
   - Leverage AWS services (API Gateway, Lambda, DynamoDB, Polly, Cognito) for seamless backend integration.
   - Utilize Google Cloud Vision AI to process and identify issues in medical images (X-rays and other medical photos).
   - Incorporate Azure AI services (Speech to Text) for transcribing doctor-patient conversations in various languages.

2. **Speech-to-Text and Image Analysis:**
   - Implement transcription and image recognition capabilities for effective patient record management.
   - Allow doctors to upload images for analysis and save the data in patients' medical records.

3. **Interactive AI Virtual Assistant:**
   - Integrate OpenAI's API for developing a virtual assistant to schedule appointments and answer medical queries.
   - Enable multi-language functionality to interact with a broader user base.

4. **User Interface Implementation:**
   - Create an easy-to-navigate frontend application that can interact with back-end services and serve as the primary interface for doctors and patients.

5. **Data Security and Compliance:**
   - Secure patient data and follow cloud best practices for storing and processing sensitive medical information, complying with HIPAA and GDPR regulations.

6. **Validation and Testing:**
   - Validate the solution through detailed testing, including voice-to-text in different languages (e.g., English, Spanish, Portuguese) and integration with AI-powered image analysis tools.

## Project Solution:
1. **Backend Implementation (Part 1):**
   - Set up serverless architecture using AWS Lambda and API Gateway, ensuring automated data processing.
   - Configured APIs to interact with Google Cloud Vision AI for medical image analysis, AWS Polly for speech-to-text, and Azure's Speech API for transcriptions.
   - Ensured secure communication between services with AWS Cognito for authentication and used CloudWatch for logging and error tracking.

2. **Frontend Implementation (Part 2):**
   - Installed and configured the frontend for managing doctor and patient profiles, registering medical records, and testing AI speech and translation features.
   - Enabled users to upload medical images (e.g., X-rays), and AI powered the back-end for analyzing these and updating patient records.
   - Implemented OpenAI's assistant for virtual appointment scheduling and handling healthcare-related queries.

3. **Multi-Language Support:**
   - Integrated speech translation and transcription tools to cater to users speaking in different languages (English, Spanish, Portuguese).
   - Managed potential cross-lingual challenges, ensuring transcription and AI-powered assistant worked flawlessly in various linguistic settings.

4. **Deployment:**
   - Used npm to deploy frontend and backend services. Deployed services using AWS API Gateway and Lambda, linked Google Cloud Vision AI, and integrated OpenAI's assistant for AI features.
   - After testing, conducted resource cleanup by emptying S3 buckets and stopping unused instances, following CloudFormation guidelines.

## Tools and Technologies:
- **AWS:** Cognito (authentication), S3 (file storage), API Gateway (integration), Lambda (serverless backend), Polly (text-to-speech), DynamoDB (database), CloudWatch (monitoring).
- **Google Cloud:** Vision AI (medical image recognition).
- **Azure:** Speech AI (transcribing doctor-patient conversations).
- **OpenAI:** Language models for AI assistant and scheduling capabilities.
- **Frontend Tools:** Vite, TailwindCSS for styling, and npm for package management.
- **Backend Frameworks:** Serverless framework for managing deployment.

## Step-By-Step Directions

### Pre-Requisites:
Ensure that the following resources and credentials are set up:
- **Azure Credentials:** For Azure services like transcription.
- **Google Cloud Credentials:** For medical image processing with Google Cloud Vision AI.
- **OpenAI Key and Assistant:** To enable virtual assistant capabilities for patient scheduling.
- **EC2 Instance Access:** For deploying application files and managing resources.

Ensure that you have your API keys and service account files ready from:
- Azure (Speech to Text and Text to Speech)
- Google Cloud (Service Account JSON for Vision AI)
- OpenAI (For creating the Assistant and integrating with your app)

## Step-By-Step Directions

### Part 1: Backend Deployment

#### Step 1: Environment Setup
- **Access EC2:** Begin by SSH-ing into the EC2 instance. Download and unzip application files.

<p align="center">
<img src="https://i.imgur.com/JKtMuml.png" height="80%" width="80%" alt="Pic"/>
<br />
<br /> 
 
<p align="center">
<img src="https://i.imgur.com/9KUkLnQ.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/uvXx7hr.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

- **Install Dependencies:** Inside the backend folder, run npm install to install the necessary backend packages.

<p align="center">
<img src="https://i.imgur.com/9lda8GY.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

#### Step 2: Configure Credentials
- **Azure Transcription:** Configure Azure's Speech-to-Text credentials. Copy your Azure Speech key and region (for example, central US) and add them into the respective configuration file for the backend.

<p align="center">
<img src="https://i.imgur.com/n6Lmk6j.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/aILt0sp.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
- **Google Cloud Service Credentials:** Set up Google Cloud Vision AI credentials by creating a JSON key. Copy the contents into the required configuration file.

<p align="center">
<img src="https://i.imgur.com/7dIuQ2p.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/7oIyXkw.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

- **OpenAI Credentials:**
  1. Log into the OpenAI platform, go to API key settings, create a new secret API key, and copy it.

<p align="center">
<img src="https://i.imgur.com/pB7ceFK.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/o5XQslR.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
  
  2. Create a new OpenAI assistant named Health Hub Assistant. Specify its goal to schedule medical appointments and use OpenAI API calls for virtual assistance.

<p align="center">
<img src="https://i.imgur.com/ZJviDf1.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
  
  3. Note down the Assistant's ID for future reference.

#### Step 3: Apply Configurations
- **Edit the configuration files for backend deployment, replacing placeholder credentials with actual values:**
  1. Azure Speech Key and Region.
  2. Google Cloud Service Account Key (JSON file content).
  3. OpenAI API Key and Assistant ID (be cautious when copying and pasting to avoid spaces).

<p align="center">
<img src="https://i.imgur.com/foWX5Hx.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/AWDBPSK.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
#### Step 4: Backend Deployment
- **Execute npm run deploy.** After successful deployment, the application should now be set up with integrated backend services including AI speech, transcription services, and medical image processing.

<p align="center">
<img src="https://i.imgur.com/eKZitLm.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
- **Check for Errors**

<p align="center">
<img src="https://i.imgur.com/xBPt1vf.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

### Part 2: Frontend Deployment and Testing

#### Step 1: Frontend Setup
- **Install Dependencies:** Inside the frontend folder, run npm install to install the necessary frontend packages.

<p align="center">
<img src="https://i.imgur.com/e2a4T8J.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

- **Configure Vite URL:**
  1. Access AWS API Gateway and copy the deployed API URL.

<p align="center">
<img src="https://i.imgur.com/Hs4jGSu.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

  2. Paste the API URL into the application configuration and save the changes.

<p align="center">
<img src="https://i.imgur.com/XtZB2yk.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/3PufsZN.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

#### Step 2: Run the Application
- **Execute npm run dev** to start the frontend development server.

<p align="center">
<img src="https://i.imgur.com/NDEYgcW.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
- **Access the application** using your EC2 instance's public IP, confirming the frontend and backend connection.

<p align="center">
<img src="https://i.imgur.com/QuP3aqx.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/3QNbtOt.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

#### Step 3: User Registration
- **Register a doctor and a patient.** (Example: Register Dr. Jean Rodriguez and patient Ava Browm).

<p align="center">
<img src="https://i.imgur.com/Ys2cAwy.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/LRlhuR7.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
- **Once registration is complete, log in as the doctor.**

<p align="center">
<img src="https://i.imgur.com/Ck5o37T.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

#### Step 4: AI Feature Testing
1. **Text-to-Speech:**
   - Input a test text in English or another language (e.g., Portuguese).

<p align="center">
<img src="https://i.imgur.com/0rhVzWm.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
   - Use AWS services to convert the text and save it to the patient's record.

2. **Speech-to-Text (Transcription) Functionality:**
   - Test transcription by uploading audio in English and Portuguese.

<p align="center">
<img src="https://i.imgur.com/I9xFwBF.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />
 
   - Ensure the transcriptions are accurate by verifying the language settings before making requests.

3. **Medical Image Analysis:**
   - Upload an X-ray image for analysis through Google Cloud Vision AI.

<p align="center">
<img src="https://i.imgur.com/NR5jUl2.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

   - Ensure that the results are automatically saved to the patient's medical record.

#### Step 5: Virtual Assistant for Appointment Scheduling
1. Log in as a patient.
2. Access the Virtual Assistant feature, which is integrated into the system to allow appointment scheduling.
3. Test scheduling by asking the assistant to show available doctors (e.g., Dr. Jean Rodriguez) and request an appointment.
4. Ensure the appointment is created and stored correctly in the system.

<p align="center">
<img src="https://i.imgur.com/U7HT5q4.png" height="80%" width="80%" alt="Pic"/>
<br />
<br />

## Conclusion
This Health Hub project integrates speech and image AI, leveraging Azure, Google Cloud, AWS, and OpenAI. By following through the step-by-step deployment and testing process, the project showcases a seamless interaction between cloud services to deliver healthcare AI tools effectively. After deploying and testing the complete solution, all associated resources have been cleaned up to maintain a tidy working environment.

This document contains all the essential steps, configurations, and cleanup procedures. By completing this project successfully, you've not only demonstrated cloud integration and AI capability but also ensured best practices for resource management.

## Challenges Encountered:
1. **Cross-Service Integration:**
   The project used services across multiple cloud platforms (AWS, Azure, Google Cloud, OpenAI), which required precise API configurations to avoid integration issues. Ensuring smooth communication between each service was essential for efficient project functionality.

2. **API Key Management:**
   Handling multiple API keys from different cloud providers led to confusion during credential configuration. Keeping these credentials secure while ensuring smooth integration was challenging.

3. **Speech-to-Text Limitations:**
   The speech-to-text API from Azure presented a delay in transcription, which affected real-time interaction. Additionally, language detection occasionally produced mixed results for languages like Portuguese and Spanish, requiring adjustments to fix issues.

4. **Handling Sensitive Data:**
   Managing and securing sensitive medical data to comply with HIPAA and GDPR regulations was critical. Implementing secure data handling practices on the cloud required constant monitoring, especially with regard to patient privacy.

5. **Multi-Language Integration:**
   Speech-to-text and translation features needed to handle diverse linguistic content. Dealing with language-specific accentuation, dialects, and idiomatic phrases posed an added challenge in ensuring accuracy for diverse regions.

## Lessons Learned:
1. **Collaborative Cloud Architecture:**
   Using multiple cloud providers in one solution requires meticulous planning and documentation to ensure smooth integration and data flow across platforms. Planning and testing cross-cloud communication thoroughly would reduce integration errors.

2. **Importance of Credentials Management:**
   Organizing and securely storing API keys and credentials is essential for maintaining security and seamless API communication. Keeping them separate for different environments (e.g., staging and production) made the deployment process easier and safer.

3. **Efficiency of Serverless Architecture:**
   Leveraging AWS Lambda and API Gateway for serverless backend functions improved scalability, reduced maintenance time, and helped maintain a cost-effective solution, especially for a small-to-medium-sized enterprise.

4. **Tailored AI Tools Make a Difference:**
   Integrating AI tools like OpenAI's assistant for automating appointment scheduling added significant value by reducing doctor and patient interactions to just a few clicks while handling common queries efficiently.

5. **Iterative Testing:**
   Performing rigorous testing on each feature separately helped detect issues early on. For instance, working with languages and AI services in parallel ensured that any language-specific problems were resolved in the design phase.

## Future Improvements:
1. **Improved Real-Time Transcription:**
   Further optimization is needed for speech-to-text transcriptions, possibly by integrating AWS Lex or other advanced AI speech recognition systems to address delays and errors in transcriptions.

2. **Full Automation of Image Analysis:**
   The AI-driven image recognition service can be expanded to automatically flag or categorize specific types of diseases or conditions in medical images, rather than just analyzing general features.

3. **Expanded AI Assistant Capabilities:**
   Enhancing the virtual assistant to answer a broader set of patient inquiries, including general health information, drug side effects, and lifestyle tips, would make the platform even more useful.

4. **Data Analytics and Reporting:**
   Adding data analytics and reporting features to visualize trends in patient health, medical visits, and historical data to help doctors provide more personalized treatment suggestions.

5. **Multi-cloud Implementation:**
   A fully multi-cloud solution, integrating not only AWS, Azure, and Google Cloud, but also other tools in seamless ecosystems, could create an optimized, more efficient platform, especially for scaling in different geographic locations.
