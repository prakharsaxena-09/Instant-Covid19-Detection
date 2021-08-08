## Inspiration
COVID-19 has infected more than 50 million persons worldwide and caused the death of more than 500,000 persons. Early symptoms of the virus include trouble breathing, fever and fatigue and over 60% of people experience a dry cough. Due to the devastating impact of COVID-19 and the tragic loss of lives, it is of the utmost urgency to develop methods for the early detection of the disease that may help limit its spread as well as aid in the development of targeted solutions.
The only way to reduce the transmission of virus is by early detection & treatment. But with people returning to normal life after the lockdown it has become quite difficult to track & trace people with COVID-19 symptoms specially in crowded & high risk places like airports, malls, metro stations, etc.
There's a very high demand to automate the testing & detection of Covid-19 symptonic  patients as well as to reduce the involvement of manual human labor in the process.
Because of all these reasons we built _'Instant Covid19 Detection'_ system.
We went through a number of journals and research papers and got to know that coughs and other vocal sounds contain pulmonary health information that can be used for diagnostic purposes, and recent studies in chaotic dynamics have shown that nonlinear phenomena exist in vocal signals. We used this feature to develop our ML based covid19 detection system.

## What it does
It is a cough detection system, which can distinguish between noise and cough sound and can help finding Corona suspect. It uses machine learning techniques for that. It can differentiate between normal background noise and coughing in real-time audio. We used Edge Impulse Studio to collect & pre-process the dataset of coughing and background noise samples and build a highly optimized TInyML model using Google Cloud's AutoML feature, that can detect a Cough sound in real-time.

## How we built it
As mentioned earlier, we are using Edge Impulse Studio to collect & pre-process the data for our cough detection model. Since the goal was to detect the cough, we collected some samples of that from Covid19 patient's interviews/vlogs on YouTube in which they were seen occasionally coughing  and some other samples for noise, so it can distinguish between Cough and other Noises.

After which we created a dataset with two classes “cough” and “noise”. To create a dataset, we created an Edge Impulse account, verified your account and then started a new project. Firstly we connected our laptop from the _'Device'_ section after which we clicked on the _'Data Acquisition'_ button to upload the data under two labels, i.e. cough & noise.

Upon completing this task we clicked on Impulse Design to add a processing & learning block respectively. Edge Impulse has several signal processing blocks that can be used to extract features from the samples acquire and learning blocks. In this case, we want to recognize the human cough, for this reason, we used Mel Frequency Cepstral Coefficients (MFCC) audio processing and as a learning block used a Neural Network (Keras).

Then we logged into the Google Cloud Console and installed the CLI Uploader. After which we linked our Edge Impulse account with the Google Cloud's account using the API Key & Edge Impulse credentials to provide the pre processed data for the Auto ML feature. We used Google Cloud's AutoML feature along with Edge Impulse to train and build the ML model as Edge Impulse's ML model was not that much accurate.

Finally after training & building the AI-ML model on Google Cloud we deployed the model using Arduino Library on the hardware part. The library was build using Edge Impulse's Arduino Deployment feature.

The hardware part was quite simple & consisted of Arduino Board as the microcontroller, microphone to collect samples/inputs, LED's to give output along with an HC06 Bluetooth module for data transmission. Some small electricals parts like  jumper wires, breadboard, resistors, etc. were also used.


## Challenges we ran into
Though Edge Impulse was self capable to train & build the ML model but then also we used Google Cloud's AutoML help as Edge Impulse's model had accuracy issues.
The main challenge that we faced in doing this was to connect Edge Impulse's Account with Google Cloud's account. We went through number of articles, videos, posts and finally one of our senior guided us in doing it. Using AutoML's feature was also quite a challenging task as we didn't had credits to use that feature free, but we used our Student's email-id to solve that problem. 


## Accomplishments that we're proud of
We are proud that we build the working prototype of our idea that could indeed help not only thousands but millions of people worldwide. It could save lifes of a number of people and could help in reducing the transmission of Covid19.
We are proud that using this device we could automate the task of detection of Covid 19 Symptonic patients in crowded places like airports, malls, railway station etc. It would not only automate task but would also minimize the involvement of manual human labor for testing at such high risk crowded places.
With colleges and universities reopening, it can be used as an automated preventive measure to detect people with covid 19 symptoms thus reducing the risk of transmission.

## What we learned
We had never used Edge Impulse Studio in the past so it was quite a new thing for us. We learned the basics of that platform and how beginners can use it to develop TinyML projects easily. We learned how to collect & clean data for our ML model and how important it is to provide the right dataset to build & train the ML Model.
Though we have worked on Arduino in the past but such a project involving Machine Learning & hardware together was something new and a great learning lesson for us. 

## What's next for Instant-Covid19-Detection
We are currently trying to incorporate a thermal scanner and a mask detector in this system to make it more accurate so that it can be installed at high risk, crowded places and can help in reducing covid-19 detection automatically without any human intervention.
