# Create Role
-----------

The Catio AWS wizard will take you through the following steps to set up the role setup.

Use the steps below to create the necessary role for Catio to assume in order to navigate your cloud environment resources. The role **must** be named `CatioConsoleAccessRole`.

!!! note "Setting the External ID" 
    The External ID is a user-defined value that you specify when creating an IAM role in AWS. The External ID adds an extra layer of security when granting temporary access to your AWS resources.   and acts as a unique identifier that helps prevent unauthorized access. Only entities that know the correct External ID can assume the role.   


### Using the CLI:

1. Generate an External ID to use to secure the integration to Catio. You can use the following command to generate a secure random ExternalId.  
**Important**: This is the only time you'll typically see or set the ExternalId so make a note of it as you will need it in the final setup step. 

See more details on ExternalId [here](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html?icmpid=docs_iam_console#id_roles_third-party_external-id):
    ```
    openssl rand -hex 32
    ``` 
2. Use the following command to create the role, make sure to replace `<externalId>` with the ExternalId generated in the previous step:
    ```
    aws iam create-role \
      --role-name CatioConsoleAccessRole \
      --assume-role-policy-document '{ "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Principal": { "AWS": "arn:aws:iam::090135924592:role/CatioPlatformAccessIRSA" }, "Action": "sts:AssumeRole", "Condition": { "StringEquals": { "sts:ExternalId": "<externalId>" } } } ] }'
    ```
3. Then use the following command to attach the correct policy to the above role. Make sure to replace `<accountId>` with your AWS account ID:
    ```
    aws iam attach-role-policy \
      --role-name CatioConsoleAccessRole \
      --policy-arn arn:aws:iam::<accountId>:policy/Catio_API_Access
    ```

### Using the Management Console:

1.  Go to the ["Create Role"](https://us-east-1.console.aws.amazon.com/iam/home?region=us-west-2#/roles/create) page on the IAM console and select "AWS Account" followed by "Another AWS Account".
2.  Enter the Catio account number: 090135924592
3.  Check the "Require external ID" box and enter a secure random string to use as an [External ID](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html?icmpid=docs_iam_console#id_roles_third-party_external-id).
4.  Select the "Catio_API_Access" policy that we created in the "Create Policy" step.
5.  Enter "CatioConsoleAccessRole" in the "Role name" field and a description for your readability.
6.  Under `Trust relationships` click "Edit trust policy" and replace the Catio AWS ID with an ARN `arn:aws:iam::090135924592:role/CatioPlatformAccessIRSA`:
    ```json
    {
      "AWS": "arn:aws:iam::090135924592:role/CatioPlatformAccessIRSA"
    }
    ```
7. Click "Update policy".