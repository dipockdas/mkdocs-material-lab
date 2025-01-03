# Add Credentials

Enter Account ID & External ID
----------------

Once all previous steps are completed, enter your AWS Account ID and External ID on the final step of the AWS setup wizard and Catio will begin scanning your cloud environment.

- AWS Account ID
- AWS External ID (created when you set up the Role)


# Cloudwatch

If you are using Cloudwatch, you can enter the Cloudwatch log groups so that Catio can search those log groups for log messages in those groups.

Enter the log group name (Eg: /aws/containerinsights/application, /aws/*), that you would like this extractor to scan.
(Wildcards are supported)
