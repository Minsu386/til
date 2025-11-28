Within Azure, there are 3 kinds of roles
1) **Classic Subscription Administrator Roles**: This is the original role system.
2) **Azure Roles**: This is an authorization system is known as Role-Based Access Controls (RBAC) and is built on top of Azure Resource Manager
3) **Azure Active Directory roles**: Azure AD roles are used to manage Azure AD resources in a directory.

**Identity Access Management (IAM)**: Allows you to create and assign roles to users.

**Azure Roles (RBAC System)**

Roles restrict access to resource actions (also known as operations). There are two types of roles:
    1) **BuiltInRoles** -- Managed Microsoft roles are read only pre-created roles for you to use
    2) **CustomRole** -- A role created by you with your own custom logic

**Role Assignment**
- Is when you apply a role to a 
    - Service principle
    - (user) group
    - user

Classic Administrators is the original role system. You should use the new RBAC when possible

**Classic Administrators have three types of roles:**
1) **Account Administrator** - The billing owner of the subscription. Has no access to the Azure portal
2) **Service Administrator** - Same access of a use assigned the Owner role at subscription scope. Full access to the azure portal.
3) **Co-Administrator** - same access of a user who is assigned 