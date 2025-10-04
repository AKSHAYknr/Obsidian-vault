
---
**AWS IAM** is a service that **controls who can do what in your AWS environment**.  
It lets you securely manage **users, groups, roles, and permissions** for accessing AWS services and resources.

---

### 🔹 Key Concepts

1. **Users**
    
    - Represents a single person or application that interacts with AWS.
        
    - Can have their own **credentials** (passwords, access keys).
        
2. **Groups**
    
    - A collection of users.
        
    - Assigning permissions to a group applies them to all users in the group.
        
3. **Roles**
    
    - Temporary permissions that can be assumed by users, applications, or AWS services (like EC2, Lambda).
        
    - Common for **cross-service access** without sharing credentials.
        
4. **Policies**
    
    - JSON documents that define **permissions**.
        
    - Can be attached to users, groups, or roles.
        
    - Example: Allow a user to read/write S3 bucket but not delete it.
        
5. **Permissions**
    
    - Determine **what actions** a user/role can perform on which resources.
        
    - Examples: `s3:GetObject`, `ec2:StartInstances`.
        

---

### 🔹 Key Features

- **Fine-grained access control** → Grant minimal privileges for security.
    
- **Temporary credentials** → Use roles for applications/services.
    
- **Multi-factor authentication (MFA)** → Adds extra security.
    
- **Integration with other AWS services** → EC2, Lambda, S3, RDS, etc.
    

---

### 🔹 Example Use Case

For your **ToolShare project**:

- Create IAM users for developers with **limited permissions**.
    
- Use IAM roles for **EC2 instances or Lambda functions** to access S3 or DynamoDB.
    
- Apply **policies** so only the payment service can access sensitive user data.