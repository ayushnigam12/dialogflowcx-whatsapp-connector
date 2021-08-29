# Dialogflow CX WhatsApp Integration with Twilio

A simple way to connect and integrate Dialogflow CX and Twilio to create WhatsApp Chatbots

## Cloud function configuration

**1.** Open the Google Console for Cloud Functions ([here](https://console.cloud.google.com/functions)) and make sure you have the Google Project of your Dialogflow CX selected.

**2.** Click on "Create Function" to open the interface for function creation.

**3.** Set the name of the function.

**4.** On the **Source Code** option, select **Inline Editor** .

**5.** In the **index.js** tab, copy and paste the code from the index.js file in this repository.

**6.** In the **package.json** tab, copy and paste the code from the package.json file in this repository.

**7.** - Set the **Function to Execute** field to the name set in Step 2.

**8.** - Click on the Dropdown "**Variables, Networking and Advanced Settings**"

**9.** - In the **Enviroment Variables** section, look for **Runtime Enviroment Variables** and click on "Add Variable"

**10.** - Copy and add the variables called:

**11.** From the DialogflowCX dashboard select the project and from the hamburger menu on the left copy the name. For e.g.
`projects/PROJECT_ID/locations/LOCATION/agents/AGENT_ID`

- **accountSid** The Account SID is given on the console of Twilio account. Refer to instruction 12 for more info.

- **authToken** The authentication token for your Twilio acconut, is given on the console of your Twilio project. Refer to instruction 12 for more info

- **projectId** This can be found after `project/` from thr URL copied above.

- **agentId** This can be found after `agents/` from thr URL copied above.

- **location** This can be found after `locations/` from thr URL copied above.

- **languageCode** This can be found on Dialogflow CX dashboard. For e.g for English it will be `en`

**12.** - To deploy the funciton you need to enable the Cloud Build API, you can find it here [here](https://console.cloud.google.com/marketplace/product/google/cloudbuild.googleapis.com)

**13.** - Allow you cloud function for public access. Here are the steps [here](https://cloud.google.com/functions/docs/securing/managing-access-iam)

**14.** - Click on your created function. Open the **Trigger** tab and copy the URL.

### Twilio configuration

**15.** - Create your free account in Twilio and from the console copy `accountSid` and `auth_token` which will be used as enviroment variables in cloud function.

**16.** - From the left menu select **messaging** and from **Try it out** select **Send a Whatsapp message**. This should open Twilio Sandblox for Whatsapp.

**16.** - In your Twilio Sandbox configuration ([link](https://www.twilio.com/console/sms/whatsapp/sandbox)), paste the URL into the "**when a message comes in**" field and click **save** and follow the instructions.

**17.** - You can now test the integration of your Dialogflow CX agent with the Twilio Sandbox's WhatsApp number.
