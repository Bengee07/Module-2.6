## Brief

### Preparation

- AWS Console


### Self Study Check In

- Q1: Explain Policies and permissions in your own word?
- Q2: What is Policies and permissions example in real world?
- Q3: What example of policy type

### Lesson Overview

By creating policies and tying them to IAM identities (users, groups of users, or roles) or AWS resources, you can manage access in AWS. In AWS, a policy is an object that, when linked to an identity or resource, defines the permissions for those objects. When an IAM principal (user or role) submits a request, AWS assesses these rules. Whether a request is approved or rejected depends on the permissions in the policies. The majority of policies are kept in AWS as JSON files. Identity-based policies, resource-based policies, permissions boundaries, Organizations SCPs, ACLs, and session policies are the six categories of policies that AWS supports.

Regardless of the technique you employ to carry out the operation, IAM policies define permissions for an action.

---

## Part 1 - Policy types

The following policy types, listed in order from most frequently used to less frequently used, are available for use in AWS. For more details, see the sections below for each policy type.

- Identity-based policies – Attach managed and inline policies to IAM identities (users, groups to which users belong, or roles). Identity-based policies grant permissions to an identity.
- Resource-based policies – Attach inline policies to resources. The most common examples of resource-based policies are Amazon S3 bucket policies and IAM role trust policies. Resource-based policies grant permissions to the principal that is specified in the policy. Principals can be in the same account as the resource or in other accounts.
- Permissions boundaries – Use a managed policy as the permissions boundary for an IAM entity (user or role). That policy defines the maximum permissions that the identity-based policies can grant to an entity, but does not grant permissions. Permissions boundaries do not define the maximum permissions that a resource-based policy can grant to an entity.
- Organizations SCPs – Use an AWS Organizations service control policy (SCP) to define the maximum permissions for account members of an organization or organizational unit (OU). SCPs limit permissions that identity-based policies or resource-based policies grant to entities (users or roles) within the account, but do not grant permissions.
- Access control lists (ACLs) – Use ACLs to control which principals in other accounts can access the resource to which the ACL is attached. ACLs are similar to resource-based policies, although they are the only policy type that does not use the JSON policy document structure. ACLs are cross-account permissions policies that grant permissions to the specified principal. ACLs cannot grant permissions to entities within the same account.
- Session policies – Pass advanced session policies when you use the AWS CLI or AWS API to assume a role or a federated user. Session policies limit the permissions that the role or user's identity-based policies grant to the session. Session policies limit permissions for a created session, but do not grant permissions. For more information, see Session Policies.

---

## Part 2 - Example of Permission and Policies


### Identity-based policies

Identity-based policies are JSON permissions policy documents that control what actions an identity (users, groups of users, and roles) can perform, on which resources, and under what conditions. Identity-based policies can be further categorized:

Managed policies – Standalone identity-based policies that you can attach to multiple users, groups, and roles in your AWS account. There are two types of managed policies:

AWS managed policies – Managed policies that are created and managed by AWS.

Customer managed policies – Managed policies that you create and manage in your AWS account. Customer managed policies provide more precise control over your policies than AWS managed policies.

Inline policies – Policies that you add directly to a single user, group, or role. Inline policies maintain a strict one-to-one relationship between a policy and an identity. They are deleted when you delete the identity.


### Resource-based policies
Resource-based policies are JSON policy documents that you attach to a resource such as an Amazon S3 bucket. These policies grant the specified principal permission to perform specific actions on that resource and defines under what conditions this applies. Resource-based policies are inline policies. There are no managed resource-based policies.

To enable cross-account access, you can specify an entire account or IAM entities in another account as the principal in a resource-based policy. Adding a cross-account principal to a resource-based policy is only half of establishing the trust relationship. When the principal and the resource are in separate AWS accounts, you must also use an identity-based policy to grant the principal access to the resource. However, if a resource-based policy grants access to a principal in the same account, no additional identity-based policy is required.

The IAM service supports only one type of resource-based policy called a role trust policy, which is attached to an IAM role. An IAM role is both an identity and a resource that supports resource-based policies. For that reason, you must attach both a trust policy and an identity-based policy to an IAM role. Trust policies define which principal entities (accounts, users, roles, and federated users) can assume the role. 


### IAM permissions boundaries

A permissions boundary is an advanced feature in which you set the maximum permissions that an identity-based policy can grant to an IAM entity. When you set a permissions boundary for an entity, the entity can perform only the actions that are allowed by both its identity-based policies and its permissions boundaries. Resource-based policies that specify the user or role as the principal are not limited by the permissions boundary. An explicit deny in any of these policies overrides the allow.


### IAM permissions boundaries

A permissions boundary is an advanced feature in which you set the maximum permissions that an identity-based policy can grant to an IAM entity. When you set a permissions boundary for an entity, the entity can perform only the actions that are allowed by both its identity-based policies and its permissions boundaries. Resource-based policies that specify the user or role as the principal are not limited by the permissions boundary. An explicit deny in any of these policies overrides the allow.


### Access control lists (ACLs)

Access control lists (ACLs) are service policies that allow you to control which principals in another account can access a resource. ACLs cannot be used to control access for a principal within the same account. ACLs are similar to resource-based policies, although they are the only policy type that does not use the JSON policy document format. Amazon S3, AWS WAF, and Amazon VPC are examples of services that support ACLs.

### Session policies

Session policies are advanced policies that you pass as a parameter when you programmatically create a temporary session for a role or federated user. The permissions for a session are the intersection of the identity-based policies for the IAM entity (user or role) used to create the session and the session policies. Permissions can also come from a resource-based policy. An explicit deny in any of these policies overrides the allow.

You can create role session and pass session policies programmatically using the AssumeRole, AssumeRoleWithSAML, or AssumeRoleWithWebIdentity API operations. You can pass a single JSON inline session policy document using the Policy parameter. You can use the PolicyArns parameter to specify up to 10 managed session policies.

A resource-based policy can specify the ARN of the user or role as a principal. In that case, the permissions from the resource-based policy are added to the role or user's identity-based policy before the session is created. The session policy limits the total permissions granted by the resource-based policy and the identity-based policy. The resulting session's permissions are the intersection of the session policies and the resource-based policies plus the intersection of the session policies and identity-based policies.

---

## Part 3 - Example of Permission and Policies

- Allows access during a specific range of dates.
- Allows enabling and disabling AWS Regions.
- Allows MFA-authenticated users to manage their own credentials on the My Security Credentials page.
- Allows specific access when using MFA during a specific range of dates.
- Allows users to manage their own credentials on the My Security Credentials page.
- Allows users to manage their own MFA device on the My Security Credentials page.
- Allows users to manage their own password on the My Security Credentials page.
- Allows users to manage their own password, access keys, and SSH public keys on the My Security Credentials page.
- Denies access to AWS based on the requested Region.
- Denies access to AWS based on the source IP address.

---

## Part 4 - Group Discussion

- Create Permission and Policies on AWS S3 Bucket or AWS MySQL


---

## Part 5 - Group Discussion

Given all the permission and policies type, choose one of the type then discuss with your teammates then share it with other team.


---
