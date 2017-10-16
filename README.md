# Aws Developer getting started
Followed with windows

## Configuring environment

### Installing the CLI

1. Download the Aws Command Line Interface (https://aws.amazon.com/cli)
2. Execute `aws --version` and should see the aws version.

### Configure the AWS CLI
1. Configure AWS Access Key (enables CLI and SDK to access the account)
2. Security Credentials under `Your name` top menu
3. Open `Access Key` menu options
4. Create new access key (the key can only be downloaded once so save it)
5. On command line `aws configure` and follow the instructions
6. `aws ec2 describe-instances` to test, you should get and empty list

## Administration

### CloudWatch 

Setup alarms and notifications or actions in response to service metrics thresholds.

- Notifications can ge send by HTTP, email, SMS...

- The actions can be auto escaling for example.

Using SNS (Simplest Notification Service) can configure where the notification goes.

The main structure on SNS is the Topic, used to create a unique amazon resource name that can have notification sent to it, once you subscribe o a Topic (with SMS, Email...) any notification that is send to SNS topic will be communicated to the subscribed end point.

#### Creating a notification
1. Select North Virginia from the top menu as the billing alarm only works on that zone at the moment.
2. Create an SNS topic with Email subscription: go to the AWS dashboard and click on `Simple Notification Service`
3. `Create a Topic`: name it and give it a description.
4. `Create Subscription`: email subscription with the email to be notified.
5. Confirm the subscription through the email you should have received to enable the subscription.

#### Creating CloudWatch billing alarm
1. Go to Services - CloudWatch
2. Click on Your name from top menu and `Billing Dashboard` - Preferences (left menu)
3. Check `Receive Billing Alerts`
4. Back to CloudWatch - Alarms - Create Alarm (You will see the services available for alarms).
5. Select `Total Estimated Charge` - Check USD as currency - Set time range for threshold eavluation - Next - set the threshold.
6. On actions select State alarm and teh name of the SNS Topic created.
7. The alarm should have been created, from now on you will be notified if the alarm is triggered.

### IAM (Identity & Access Management service)

Setup access policies on the AWS account.

Methods to control permissions:
 - Policies: rules to access a service by users/groups.
 - Got to `Services` -  `IAM` to see the dashboard.

 #### Securing the account:
 Root account (one that was created when the account was opened) need to be protected:
 1. Multifactor authentication: setup MFA from the dashboard.
 2. Sign out and try to sign in again.

### Policies
- You should at least assign a Policy to a user, by user or by role.

#### Policy Statement properties
- Effects: allow/deny
- Action: operation that the user can perform on a service
- Resouce: specific resource user can perform action on

There are precreated policies but you can create your own policies.

1. `Services` - `(IAM) Identity & Access Management` - Policies
2. Have a look at some of the policies (json) to explore

#### Securing the account:
Amazon doesn't recommend to access your account with the account that was created.
1. Create new user.
2. Create new group with appropiate permissions
3. Assign group to user
4. Setup expiration password policy
5. On the dashboard there is a link that you can copy in order to login into your app with the user created