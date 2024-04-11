## Building a Machine Learning-Enabled Web App: AcadeML

This repo contains app code to accompany AWS Workshop Studio [Building a Machine Learning-Enabled Web App](https://studio.us-east-1.prod.workshops.aws/workshops/b0b09da3-8c15-4c6a-aaf1-c265fe6e595d).  
As this is a standalone repo, it can be used without AWS Workshop Studio.

There are currently 2 labs in the workshop:
1. Lab 1: Adding **Amazon Rekognition** to an existing web app
2. Lab 2: Adding **Amazon Textract** to an existing web app

### Audience
This is a foundational repo aimed at students learning how to call ML APIs and interpret JSON returned for the first time.

### Technology and Services
The app stack:
* Node.js, Javascript, AWS SDK V3 (Javascript)
* Vue.js, Vuetify.js, and Vite

### Prerequisites
The following software is required:
1. [Node.js](https://nodejs.org/en/download)
1. The app requires an AWS account to run:
    1. If you are attending an AWS Workshop event, this is supplied to you. 
    1. If you are using this repo outside of an hosted Workshop event, you will need to supply your own AWS account: [Create](https://aws.amazon.com/resources/create-account/) a new account or [sign in](https://aws.amazon.com/console/) to your existing account.

> Warning: The repo calls AWS services, which incur a cost. While briefly running the app as a learning exercise would only incur a relatively small cost, care should be taken to monitor spend and delete AWS resources and associated services when no longer needed to ensure future charges do not accrue.  

### Branches
There are 2 branches in this repo; `start-lab` and `complete-lab`.  
The `start-lab` branch contains the web app *without* the code for calling ML APIs.  
The steps to add this code are in the workshop referenced above.  
The `complete-lab` branch contains the final code the student would have at the end of the lab.  

### Installation
1. Clone the `start-lab` (or `complete-lab` if not attempting the workshop) branch into a new folder:
    1. `git clone --single-branch --branch start-lab https://github.com/build-on-aws/building-a-machine-learning-enabled-web-app`
1. In the repo root folder run: `npm install`    

### AWS Credentials
If you are attending a hosted workshop, an AWS account with an IAM user with the correct permissions will be supplied to you.  
If attempting to run this independently, you will need to supply your own AWS account.  

In the AWS Console:
1. Create an IAM user with policies **AmazonRekognitionFullAccess** and **AmazonTextractFullAccess** attached.
1. Create an access key and secret access key (copy these before navigating away from the page)
1. Create a file in the **root** folder of the app called `.env.local` (note the `.` before the word `env`).
1. Add the following lines to `.env.local`:
* VITE_AWS_ACCESS_KEY_ID=AccessKeyFromStep2
* VITE_AWS_SECRET_ACCESS_KEY=SecretAccessKeyFromStep2
* VITE_AWS_REGION=us-east-1

### Running
1. In the repo root folder run  **npm run dev**
1. Open the localhost website (http://localhost:3000 is the default)

### Clean-up (non-Workshop Studio users)
Delete the AWS IAM user that was created by the installation steps above when you no longer need this app.

## Security
See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License
This library is licensed under the MIT-0 License. See the LICENSE file.


## Run App
Enter Run Task into the Command Palette and press enter. Select npm and then npm: dev and press enter
If you are asked to continue with a long list of options, just select the first one and press enter
This will create a new terminal process in VS Code and a message should appear similar to this in the terminal below:

VITE v3.2.7  ready in 530 ms

  ➜  Local:   http://localhost:3000/
  ➜  Network: use --host to expose

To see the app in action, CTRL + Click the URL (or copy and paste it into your web browser).
Ensure the app loads and you can see the web page is rendered and you can click on images and buttons.
The next section will describe how to use the app, but for now, stop the app:

In order to stop the npm dev run task, click Kill Terminal icon that looks like a bin (trash can) in the top right hand corner of the task window.


## Try it out

1. If not already running, in VS Code Command Palette, Run Task: and npm: dev.
2. Open the app (usually http://localhost:3000/ ).
3. The app allows the following actions by default:
    a. Select a sample image from the list by clicking on it (the image in the bottom panel should change)
    b. Click the < and > arrows on the list to scroll through the different sample images
4. Add your own image to the list by choosing it with the file picker (click Choose image from your device) and then ADD TO IMAGE LIST
    a. Note: Only PNG and JPG images may be uploaded. Each file must be 5MB or less.
5. Send the image for object labelling by clicking Detect Labels
6. Send the image for text recognition by clicking Detect Text
7. Click LABELS or TEXT to see the results after sending an image for analysis