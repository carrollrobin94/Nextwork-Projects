<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](https://nextwork.ai/projects/51a5fd24-7458-58a6-8653-9b90119a0e4a)

**Author:** Carroll Robin R  
**Email:** carrollrobin94@gmail.com

---

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1c864649)

## Introducing Today's Project!

### Project overview

In this project, I will create a EC2 instance which emulates a virtual operating system or a server, but I have to control who does what to that virtual system, so by using IAM, I will control who will be authenticated and who shall have permissions to do any modifications to the virtual system. I'm doing this project to learn the basics of cloud security through AWS IAM.

### Tools and concepts

Services I used were EC2 Instance and IAM. Key concepts I learnt include were creating a EC2 instance, the use of tags for organizing the instances, setting up IAM policy using JSON to allow only the necessary permissions. Creating an IAM User Group and attaching the IAM Policy to it. Creating an IAM User whom is added to the IAM User Group. Later we login as the IAM User to test if the policies created in IAM policy are working as intended. Finally we use the IAM Policy Simulator to troubleshoot the current IAM Policy we are using.

### Project reflection

This project took me approximately 2 hours.It was most rewarding to create the IAM policies because it is essential to prevent unauthorized access or unnecessary operations in this current world. I was surprised that after writing the JSON code in the IAM Policy, it took care of this rogue IAM user trying to delete the production instance but failed because the policy only allows the necessary operations to be performed. 

## Tags

### What I did in this step

In this step, I will be launching two EC2 Instances, one of them is the development instance and the other is production instance. We are creating them so that we can configure the development instance to handle the increased traffic and after ensuring that it works, we shift it to the production instance.

### Understanding tags

Tags are labels that we attach to resources for organization purposes. They make it easier to search and filter the resources to the particular one we are looking for. It also helps with cost allocation and applying policies based on the environment types.

### My tag configuration

The tag I’ve used on my EC2 instances are env and Name The value I’ve assigned for my instances are development and production for the tag env and for the tag Name, I used nextwork-prod-carrollrobin and nextwork-dev-carrollrobin

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_2e0e5a5d)

## IAM Policies

### What I did in this step

In this step, I will allocate the intern access to the development instance through AWS IAM policy and also include any other statements to prevent any errors from occuring because if I grant total control over the development instance, the intern might affect other development groups from doing their testings.

### Understanding IAM policies

IAM Policies are used to grant or deny permissions to operations such as modification, creation and more, executed by a select group of people. It helps to prevent any unauthorized users from taking advantage of the cloud resource.

### The policy I set up

For this project, I’ve set up a policy using JSON 

### Policy effect

I’ve created a policy that allows the creation of an EC2 Instance and describe the EC2 Instance. Denied the creation of new tags and deletion of existing tags.

### Understanding Effect, Action, and Resource

The Effect tells us if it will Allow or Deny a certain action, Action is the, in this case EC2 instance being created or a Delete tag operation denied, and Resource specifies to which is this policy applied to, for example "*" means to everyone including the root user.

## My JSON Policy

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1c864649)

## Account Alias

### What I did in this step

In this step, I will create a Account Alias for the intern to be able to access the resources of the company.

### Understanding account aliases

An Account Alias is a memorable user friendly URL used to log into the AWS Account of the company. It's main function is for the interns to be able to remember it whenever they need to access the AWS console.

### Setting up my account alias

Creating an account alias took me just a few moments as it was on the right hand side of the IAM Dashboard.Now, my new AWS console sign-in URL is nextwork-alias-carrollrobin

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0eb4439b)

## IAM Users and User Groups

### What I did in this step

In this step, I will create a IAM Group to place new IAM users inside and create a IAM Policy to ensure that they have only the required permissions to the AWS instances. I will also create a IAM user for new interns so that they are able to login to the instances. 

### Understanding user groups

IAM user groups are folders in which we add new IAM Users to ensure that they have only the required permissions to the AWS resources of the company.

### Attaching policies to user groups

I attached the policy called NextWorkDevEnvironmentPolicy which allows and denies certain operations. I created to this user group called nextwork-dev-group, which means the new IAM Users who are added to the group have the required permissions to conduct their development operations and not more such as creating a new instance but they can't create new tags or delete existing tags.

### Understanding IAM users

IAM users are the identity we create for the people who need to login to the AWS resources of the company to test features in the development instance and also for the people who work in production instance to deploy the features.

## Logging in as an IAM User

### Sharing sign-in details

The first way is to email the IAM User's sign-in details to the required individual, AWS provides this service after creating the User's login details. The second way is to send a .csv file to the individual.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed that under Cost and Usage section, nothing was visible and it was replaced with Access denied, same goes for accessing the EC2 dashboard. This error appears because the new IAM User isn't supposed to have access to these services or sections as we have configured in the IAM policies for this particular IAM User Group.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_6f2ab446)

## Testing IAM Policies

### What I did in this step

In this step, I will login to AWS using the intern's IAM user details because I have to test the intern's access to the production and development instance to ensure that the IAM policies are working as expected.

### Testing policy actions

I tested my JSON IAM policy by signing up as the new IAM User to the AWS Console. First I tried to delete the production Instance,but a error message came up saying that I am not authorized to do this. Second, tried to stop the development Instance and it worked.

### Stopping the production instance

When I tried to stop the production instance, a large red box appeared which told me that it failed to terminate (delete) an instance because I am not authorized to perform this operation.This proves that the IAM policies are working correctly.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance, a pop up message appeared and said it succesfully initiated stopping of the development Instance.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1811801c)

## IAM Policy Simulator

To extend my project, I'm going to test IAM policies in a IAM Policy Simulator. I'm doing this because I want to know the extra tools that I can use to better safeguard users against any mistakes occuring in a real company's AWS resources.

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is used for testing out IAM policies on a safe place rather than a real server, saving costs. It also points out which JSON statement is causing the operation to be allowed or denied thus we are able to verify if it falls under the Principle of Least Privilege.

### How I used the simulator

I set up a simulation for DeleteTags and StopInstances. The initial results were both denied which was correct for Deletetags as the IAM policy stated that an IAM user cannot delete tags But he should be able to stop instance of development, so I had to adjust the Conditions section and set the Condition Key Value as development. Now the final results was Access denied for DeleteTags and Allowed for StopInstances.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_069d8a621)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/51a5fd24-7458-58a6-8653-9b90119a0e4a)*
