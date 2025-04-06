<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** calvinbhwilliams@gmail.com  
**Email:** calvinbhwilliams@gmail.com

---

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_1c864649)

---

## Introducing today's project!

### What is AWS IAM?

Services I used were:
💻 EC2 instances
📏 IAM Policies
👩‍👩‍👧‍👧 IAM Users and User Groups
🔖 AWS Account Alias 


### How I'm using AWS IAM in this project

This project took me approximately an hour and a half to complete. The most challenging part was navigating the AWS console, but has many similarities to systems that I have used in my day to day work activies like using Active Directory and Microsoft 365 Admin Center. It was most rewarding to apply my knowledge on other systems and gain more hands-on skills.

### One thing I didn't expect...

I chose to do this project today because I'd like to build my portfolio to help show off my skills to recruiters.

### This project took me...

---

## Tags

Tags are can be used to label our AWS resources. In my case, I created a tag call Env with the value of developent for the nextwork-dev-calvin EC2 instance I've launch. I also create a tag for my production instance. 

Tags make it easy to know the purpose of an instance at a glance and manage our instances more effectively.

The tag I’ve used on my EC2 instances is called Env and the value assigned is production and development. This represents the environments the different environments used within the organization.

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

IAM Policies are rules that define what actions a user is allowed to take with certain resources.

### The policy I set up

For this project, I’ve set up a policy using JSON.

I’ve created a policy that gives a user access to take any action on an EC2 instance that is tagged as an development environment.

### When creating a JSON policy, you have to define its Effect, Action and Resource.

The Effect, Action, and Resource attributes of a JSON policy means our we allowing or denying a certain action or permission and what resource will be effected. In this case, our resource is the development environment.

---

## My JSON Policy

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_1c864649)

---

## Account Alias

An account alias is a friendly name that can be used instead of the Account ID.

Creating an account alias took me seconds to created. Now, my new AWS console sign-in URL is https://nextwork-alias-calvin.signin.aws.amazon.com/console.

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### Users

IAM users are people who will get access to our resources.

### User Groups

IAM user groups are collections of IAM users that allows us to give permissions to the group collectively by attaching policies to the group rather than individual users. This helps save time instead of having to perform the same actions one by one.

I attached the policy I created to this user group, which means everyone I add to this group will have the policy applied to their account.

---

## Logging in as an IAM User

The first way is by emailing the sign-in instructions. The second way is by downloading a CSV file.

Once I logged in as my IAM user, I noticed that access to several services were denied.

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

I tested my JSON IAM policy by attemping to stop each instance under the IAM user I created.

### Stopping the production instance

When I tried to stop the production instance I was given an error stating that I was not authorized to perform the operation. This is because of the IAM policy I added to the group. It only allows actions to be taken on the development instance but we trying to make changes to the production instance. This would be a major problem if the IAM policy was not in place.

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_0e7a9d6a)

---

## Testing IAM Policies

### Stopping the development instance

Next, when I tried to stop the development instance, the action was allowed.This was because the the IAM user has the proper permission to make changes to the development environment.

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_1811801c)

---

## The IAM Policy Simulator

The IAM Policy Simulator is a tool to validate policies without affecting your actual AWS resources. It's useful for testing the permissions that applied to your IAM groups.

### How I used the simulator

I set up a simulation for the IAM policy that I created with my IAM user performing DeleteTags and StopInstances actions. The results were the user was denied each action because the user can only stop the development instance. I had to adjust tag setting to account for the development resource tag. This gave the user access to stop the instance during the test.

![Image](http://learn.nextwork.org/nostalgic_blue_daring_sea_lion/uploads/aws-security-iam_069d8a621)

---

---
