# Kaodim-test
this repository is built to solve an interview question from Kaodim

Architecture Question (1/2):

 This ask is to build the entire infrastructure from covering various aspects of a general IT setup. I see two aspects in the question to be considered while we are designing the setup.
  1. A secure and common platform accessible for the entire team.
  2. A decoupled platform segregated by teams specific to their own domains.
  
Solution:

I will try to keep this concise and precise. We can talk on the soution during the technical discussion I believe.

We can maintain a master account that controls and manages it's child accounts via needed cross account policies. 
whatever we plan to deploy can be done using any IAAS service (cloudformation, Terraform etc) from master to slave accounts which will ensure security and de coupling. We can easily seperate what can be seperated. 

We can discuss on above approach in details but writing it down piece by piece is not ideal expectation (I am guessing here).

Below can be the answers to the questions (again sorry these are concise and precise. Can discuss more on these).
Which environments would you use? -- the no of environments and their functioning depneds the complexity and how sensitive our setup is. But we will have to make sure we enable Blue Green Deployment (Production1 and Production2) along with Development, Testing. There might be a need of sandbox environment(again depends on the requirement). 

How you would split and divide the tools?   -- As I see Cloud and On-Premise, we need to carefully select the tools that are compatible in cloud as well as On-Premise. For example we might go with AWS Codebuild for our CI/CD because it is serverless but we need to jenkins for this and pay for the server. we can always connect our On-Premises with Cloud using Direct connect, VPN setup etc.
Split -- We can split the setup by each domain in different VPCs and enable VPC peering. The centralized VPC can have the tools shared/ accessed by all other VPCs.


Which automation systems or tools to manage the systems? -- This is a very generic question and we have to decide per domain. We can in general implement Terraform or Serverless so that it will not be specific to any cloud platform (useful if we want to move to another cloud or if we operate between different cloud environments).
Ansible as Configuration Management Tool, Datadog for capturing logs, Integrate the logs with slack when needed etc..

Again we need to decide above tools by leveraging their competitors based on the situation.


How these would be connected between them so employees can access it from the offices but also on the go? -- Simple answer would be by enabling the federated accounts using the sercured SAML authentication.

