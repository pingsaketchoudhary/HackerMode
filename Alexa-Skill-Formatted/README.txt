(`-').-> (`-')  _           <-.(`-')  (`-')  _   (`-')     <-. (`-')             _(`-')    (`-')  _ 
 (OO )__  (OO ).-/  _         __( OO)  ( OO).-/<-.(OO )        \(OO )_      .->  ( (OO ).-> ( OO).-/ 
,--. ,'-' / ,---.   \-,-----.'-'. ,--.(,------.,------,)    ,--./  ,-.)(`-')----. \    .'_ (,------. 
|  | |  | | \ /`.\   |  .--./|  .'   / |  .---'|   /`. '    |   `.'   |( OO).-.  ''`'-..__) |  .---' 
|  `-'  | '-'|_.' | /_) (`-')|      /)(|  '--. |  |_.' |    |  |'.'|  |( _) | |  ||  |  ' |(|  '--.  
|  .-.  |(|  .-.  | ||  |OO )|  .   '  |  .--' |  .   .'    |  |   |  | \|  |)|  ||  |  / : |  .--'  
|  | |  | |  | |  |(_'  '--'\|  |\   \ |  `---.|  |\  \     |  |   |  |  '  '-'  '|  '-'  / |  `---. 
`--' `--' `--' `--'   `-----'`--' '--' `------'`--' '--'    `--'   `--'   `-----' `------'  `------'

Welcome to Hacker Mode

Unleash the power of innovation with Hacker Mode, an advanced Amazon™ Alexa™ skill crafted specifically for tech enthusiasts and cybersecurity professionals. Designed by Saket Choudhary, this skill invites you to explore the depths of hacking knowledge and contribute to building a cutting-edge tool for the future.

What is Hacker Mode?
Hacker Mode is an Alexa skill that empowers you to interact with Alexa on technical topics, from encoding tips to command-line assistance for tools like Metasploit™, Nmap, and NetCat. Simply say, "Alexa, hacker mode," and dive into queries like:

“How do you perform a service fingerprint scan with Nmap?”
“What is the HTML encoding for a double-quote?”
This skill isn’t just an app—it’s a collaborative project aiming to redefine how technical knowledge is accessed and shared.

How It Works:
To use Hacker Mode, you'll need:

An Alexa Skills Developer Account to upload the skill's interaction model (JSON-based invocation examples).
An AWS account to host the program logic as a Node.js Lambda function.
An Alexa-enabled device (e.g., Echo, Dot, or Tap).
Links to relevant Amazon resources will be provided for setup.

Contribute and Collaborate:
Whether you’re a cybersecurity expert, a coding enthusiast, or someone curious to explore the tech world, Hacker Mode offers you a chance to be a part of something transformative. Contribute to its development, refine its capabilities, or simply enjoy its advanced functionality as it grows to become the go-to tool for hackers worldwide.

Are you ready to join the movement? Dive into the challenge, contribute your expertise, and help Hacker Mode take over the world (ethically, of course).

Continue if you dare...


====================
What is Hacker Mode? \  (the name of the project and the name to invoke the Alexa skill)
======================================================================================================

Hacker Mode is a collection of Node.JS code and JSON that builds two important pieces of a whole:
Overview of the Alexa Skill and Lambda Function
This project consists of two key components:

1) Alexa Skill
The Alexa Skill is the interface between the user and the logic behind the scenes. It defines how Alexa interprets and processes user voice commands. The skill comprises three main elements:

Intents

These define the categories of actions or queries the user might perform.
A JSON file describes the different types of requests the skill can handle.
It also references specific lists that help provide detailed responses.
Sample Utterances

These are examples of how users can phrase their questions or commands.
This file maps natural language expressions to the corresponding intents.
Item Lists (Slot Types)

These are predefined lists of words or phrases Alexa will recognize within specific contexts.
They act as the "subjects" or "keywords" for user questions, helping Alexa provide accurate responses.
2) Lambda Function
The Lambda function serves as the backend logic that processes the user's voice requests and generates responses. It works seamlessly with the Alexa Skill to deliver results.

Hacking.js
This single JavaScript file is the core Lambda function.
It consumes a JSON payload (representing a user's voice request) sent by Alexa and processes it.
Based on the intent and slot data, it formulates and returns the appropriate response to Alexa.
How It All Works Together
A user interacts with Alexa using a command that matches a sample utterance.
The utterance triggers a specific intent defined in the skill's JSON model.
Relevant slot types are identified to process the user's query accurately.
The intent and slots are packaged into a JSON request and sent to the Lambda function.
The Lambda function (via Hacking.js) interprets the request, executes the necessary logic, and sends the response back to Alexa.


==============================
App Structure and First Steps \
======================================================================================================
I have broken out the files into Two directories to match the basic structure (Lambda and AlexaSkill)  The interesting thing is that these two pieces of an Alexa app are in fact created and tested IN TWO SEPARATE WEB SITES!  

******************************************************************************************************
You create your Alexa Skill in: https://developer.amazon.com/edw/home.html#/skill/
  Log in there create an Alexa function named HackerMode
  Enable the Beta Skill builder
  In the SkillBuilder portion of the web site click on the "code" and paste in the HackerModeIntents.json contents into the coding area.
  Save and Build the "Intent"

And create your Lambda expression in: https://console.aws.amazon.com/lambda/home?region=us-east-1#/functions/
  Log in there (should be the same account email and password)
  Create a Lambda expression using a template for a JSON Alexa app (I think it's the color picker example)
  Paste in the Hacking.js contents and name your function fnHackerMode or whatever.
  Make sure your function has a role set for it. (AWS guides you through creating a basic role to run it)
Steps to Configure and Enable Your Alexa Skill
Link the Lambda Function to the Alexa Skill

Ensure the ARN (Amazon Resource Name) for your Lambda function is correctly entered in the Alexa Developer Console under the skill’s endpoint configuration.
This step ensures that the Alexa Skill routes voice requests to the correct AWS Lambda function for processing.
Test and Enable the Skill

Once the skill is created and linked to the Lambda function, download the Alexa app on your smartphone.
Log into the app using the same Amazon account you used to create the skill and Lambda function.
Go to the "My Skills" section in the app, locate your newly created skill, and enable it.
This activation process ensures the skill is available on your Echo devices or any Alexa-enabled devices linked to your account.
Account Synchronization

It is critical to use the same Amazon account for:
The Alexa Developer Console.
The AWS Lambda console.
The Alexa app on your phone.
If accounts are not synchronized, the skill might exist but will not appear in the Alexa app, preventing it from being enabled on your devices.
Stay Updated

Amazon frequently updates the Alexa Skill and Lambda setup process, which may lead to minor changes in these steps.
If you encounter issues, refer to recent tutorials or video guides on platforms like YouTube for the latest walkthroughs.

  
*************************************************************************************************************
I recommend before you start on your road to Alexa skill building that you use one of their built-in samples to get an idea of how it works. Bookmark both sites as you'll have them open a lot during development and you'll be cutting and pasting code into the sites. 

================
Getting Started \
=====================================================================================================
Once you have your feet wet, and have tested a "demo" skill on your Alexa device... From there, you can create a new skill and preferably call it Hacker Mode and drop the lambda code in on the AWS side and link the two with AWS Lambda ARN number that is generated when you create the Lambda expression. This basically marries the Alexa skill in the skills web site to the logic in your Lambda expression on the AWS site.

Amazon has some good tutorials (and free swag apparently):
https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/content/fact-skill-1?&sc_channel=SEM&sc_campaign=Fact-Skill&sc_detail=Branded&sc_segment=Alexa-Tutorial&sc_publisher=Google&sc_country=WW&sc_medium=SEM_Fact-Skill_Branded_Alexa-Tutorial_Google_WW_0007&sc_trackingcode=0007&gclid=CMOFndDV1dMCFViRfgodZrIDLQ

This one is not too bad: 
https://www.pluralsight.com/guides/node-js/amazon-alexa-skill-tutorial


When you start your Alexa it will pick up the list of skills from your account on the skills web site. The Intents, utterances in the JSON file tells Alexa how to assemble a JSON request that can be consumed and translated into something useful by the Lambda "program". Basically, when a request comes in, the Lambda server "wakes" the lambda logic and "runs" it on the incoming JSON. If the Intent is one that it has a function handler for, it will try to match the ITEM that comes in to a list of items in the lambda code and respond with whatever the prescribed answer is for that combination of INTENT and ITEM.

To shed more light on this: If you want Alexa to be able to answer the question "who's the greatest {talent} of all time?" you would break that down into an INTENT called: "TheGreatest"
You'd create a list of things to fill in the blank with ... like: hockey player, hacker, singer

You'd create a set of sample utterances using the Beta Skill Builder in the Alexa Skill web site. Then you'd tailor your Lambda expression code to match the {talent_list} named items like: hacker, singer, hockey player to your list of responses in your lambda's JavaScript code.  In this case I do it with a database built out of JSON objects and I have a row named for each possible option that includes a speech response and sometimes even also includes a text response.

Anyway, peek through the code and it will start making sense.  It really comes together once you've set up one of Amazon's provided demo projects like Favorite Color.

================
Further in Depth\
======================================================================================================

The heart of the Lambda expression is basically a program inside of a JSON object. Which is weird but bear with me. (We live in a JavaScript world)  JSON, for those that aren't familiar is a basically a less wordy version of XML. And as such, it can hold data in various forms.

The goal of the Lambda expression is to provide a means of accessing your answer data that Alexa will speak back, and to trip a function of the program or a "handler" to handle a specific INTENT type. So, going back to the example of the "TheGreatest" intent example, you'd have a function in Javascript within the Lambda expression that is tagged with that intent name. As the Lambda interpreter loads your expression and tries to match what is being asked with possible responses it sees there's a match and fires the logic of your function to respond to the incoming INTENT type and ITEM type. In this case INTENT is "TheGreatest" and ITEM is "hockey player". Your Lambda expression function will then look up in a data structure the answer for that query which is "Wayne Gretzky".

At the very bottom of the Lambda expression included in this project you'll notice a bunch of constants defined which determine the way JSON structures map to variables. The intent is not to make it more complicated, but rather to provide a means of mapping translations to the data structures into other languages. I gave up on that idea early on and hard coded the mappings. Eventually, when we get fancy, I want to separate out the JSON data definitions into separate files to make it easier to edit them. But for now I wanted to simplify the idea of what's happening and simplify the replacing of the Lambda expression with a simple copy and paste instead of uploading a structured zip file which is the only alternative.

=======================
What is Basically Done \
======================================================================================================
Mostly done are: 
 NetCat
 NMAP
 Metasploit
 Html Encodings
 Hex Encodings
 ASCII encodings
 URL encodings
 HTTP Headers lookup
 HTTP Verbs lookup
 TCP/UDP Ports (common)
 IP Lookup (GeoLoc)
 Rick Rolling 

 Upgrading the intent code to support the new Beta skill builder capability

======================
What Needs to Be Done \ 
======================================================================================================
I want to finish:
 all TCP/UDP ports
 HTTP response codes
 UU char encodes
 IP to IntegerIP value conversions 
 Powershell goodies
 WMIC commands
 Shodan lookup for an IP
 Lin/Win commands for basic user creation and system management
 *commands for every decent hacker tool out there like nCat an upgraded netcat with HTTPS support
 *commands for "living off the land" like creating a web server using OpenSSL :)
 ** commands for actually kicking off a scanning a local subnet target with nmap maybe on your own Kali
 *** a command language for auto-pwning local subnet systems which would require a CNC server with strong crypto and message verification.

In short, let's make this the new pen testing framework shall we?
When I think of where I want this to go, I want to get beyond just curiosity questions like what is the hex encoding for carriage-return, but get to weightier matters like:

"Alexa, Hacker Mode..."
	"Now in hacker mode..."
"autopwn 192.168.0.11 for me"
	"Are you sure you want to autopwn 192.168.0.11?"
"Yes, I'm sure."
	"You are now root on 192.168.0.11."
	"What would you like to do?  Copy files, scan a target or create a user?"

YOU GET THE IDEA!!! SKYNET without the guns and robots BASICALLY...

========================
How to Make that Happen \
=======================================================================================================
Responsible Usage of AWS Lambda for Your Alexa Skill
It’s important to acknowledge that integrating hacking logic into a Lambda function is both unethical and likely to get you into legal trouble. Amazon has strict policies against misuse of AWS resources, and attempting to bypass these could result in permanent account suspension or legal consequences.

Responsible Use Guidelines:
Keep Penetration Testing Local:

If your Alexa skill involves penetration testing or network scanning, ensure all operations are conducted locally on your own machine.
Use your laptop or personal server where you take full responsibility for actions performed.
Ensure you have explicit, written permission to scan any network you target. Scanning networks without proper authorization is illegal and could result in severe penalties.
Avoid Misusing AWS Resources:

Do not attempt to perform any unauthorized activity through Lambda or other AWS services.
You may use Lambda to trigger actions on your locally managed Command-and-Control (CNC) server, which can then execute approved scans or commands on your authorized networks.
Building Your Alexa Skill Safely:

Use your own branches, personal hardware, and resources to test advanced features like network scanning.
If you’ve developed a safe and responsible version of the skill, you can submit a pull request to the main repository for review.
Any malicious or unsafe code, such as one that attempts unauthorized actions from AWS or external servers, will be outright rejected.
API and Third-Party Service Restrictions:

If your code relies on external APIs or web services, ensure you have explicit, perpetual written permission to use them. Without this, such features will likely be rejected during review.
Be cautious: third-party services may suddenly revoke access or impose charges for excessive usage. Always verify terms of use to avoid unexpected costs or legal complications.
AWS Free Tier Considerations:

AWS offers a free tier for Lambda with approximately 1 million free requests per month. Keep track of your usage to avoid accidental charges.
Monitor the runtime of your Lambda functions. Amazon may flag functions with prolonged execution times, potentially moving them out of the free tier sooner than expected.
Key Takeaway:
Build responsibly, test ethically, and always operate within legal and moral boundaries. If you’re enhancing your skill for personal use, do so on your own infrastructure with clear accountability. For shared contributions, ensure they meet ethical and practical standards, benefiting the community without crossing into unsafe or unlawful territory.

==================
About the License \
======================================================================================================
Ok, I understand that including a more restrictive license instead of a permissive one may seem unconventional. However, my intent is to ensure that the hard work and dedication invested in this project aren’t exploited for commercial gain without giving back to the community. The goal is to keep this project aligned with its original purpose—advancing the understanding and recognition of Red Teaming, bug bounty programs, and ethical hacking as a whole.

This initiative is meant to spark interest, raise awareness, and encourage collaboration in the cybersecurity space. If, at any point, there’s an opportunity to evolve this project into something larger, I’m open to discussing new ideas and directions for its growth.

India 
Saket Choudhary 
I.E. Panther






