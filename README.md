# Best Practices
## Identity and  Access Management
### 1) IAM user
- Pre-create groups for all the major IAM roles that you want to use at the folder level
- Use groups, not users; grant predefined roles or custom roles to groups in the Cloud console and manage group membership in the admin console
- Grant roles to a Google group instead of individual users when possible. It is easier to add and remove members from a Google group instead of updating a Cloud IAM policy to add or remove users
- If you need to grant multiple roles to allow a particular task, create an AD group, grant the roles to that group, and then add users to that group
- Granting the owner role to a member will allow them to modify the IAM policy. Therefore grant the owner role only if the member has a legitimate purpose to manage the IAM policy
- Create a use case-specific service account and assign it with only required permissions. Service accounts provide programmatic access to resources and data that is accessible via Google's APIs
- Creating service accounts any time an application or a VM instance requires access to a Google API, for instance, transacting with configurations or data contained in the GCP environment
- Consider creating service accounts similar to how authorizations are made for users, using the principle of least privilege
# 2) IAM Service Accounts
Limit who can set IAM Policy and act as a service account
Grant each service their service account per environment
Grant permissive scopes to instances and restrictive IAM roles to the service account
Restrict who can act as service accounts. Users who are granted the Service Account User role for a service account can access all the resources for which the service account has access. Therefore be cautious when granting the Service Account Actor role to a user.
Restrict who has access to create and manage service accounts in your project
Treat each component of your application as a separate trust boundary. If you have multiple services that require different permissions, create a separate service account for each of the services so that they can be permitted differently
Networking
