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

## Part 3 - Group Discussion

Insert Instructions
