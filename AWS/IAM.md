AWS

## IAM

### User
### Group
### Role
### Policy
Types:
1. Managed policies
  - AWS managed policies
  - Customer managed policies
2. Inline policies
3. Resource-based policies

1. Managed policies.
    Can be attached to (multiple) users, groups and roles
    Cannot be attached to resources
    AWS Managed Policies are managed and updated by AWS
    Customer Managed Policies are managed and updated by the customer
2. Inline policies
    Customer managed policies, one-to-one relation between policies and principal resources
    Directly attached to only a single, user, group or role
    Deleted when the resource is deleted
3.  Resource-based policies
    Inline policy type, attached to a particular resource.

Policy contains at least one statement, every statement grants permission to different
(sets of) resource(s).


ARN:
Amazon Resource Name, unique identifier for an Amazon Resource
```
arn:partition:service:region:account-id:resourcetype:resource
```
|term|explanation|
|---|---|
|partition| Which partition the resource belongs to, e.g. `aws`: public aws, `aws-cn` AWS China, `aws-gov` AWS GovCloud|
|service| Specified AWS Service name, e.g. EC2, IAM, S3|
|region| The AWS region this resource is in. Global resources (such as IAM), don't have a region|
|account-id| 12 digit AWS account number|
|resource, resourcetype:resource, resourcetype/resource| Differs from service to service|

A policy contains:
```
{
    "Version": "IAM policy language version",
    "Statement": {
        "Effect": "Whether the action on the resource is allowed or denied",
        "Action": "List of actions for a given resource",
        "Resource": "Arn"
    }
}
```

## STS
STS (Security Token Service) is a webservice that enables an application to dynamically generate temporary security credentials with restricted permissions based on an IAM Role.
- Expire after a given time (ranging from minutes to several hours)
- When expired, all acces is lost and the credentials need to be requested again

Pros:
- Dynamically create credentials
- No need to rotate
- No need to create AWS identities for your users. The credentials are namespace by user, so they can only access their own data/services
