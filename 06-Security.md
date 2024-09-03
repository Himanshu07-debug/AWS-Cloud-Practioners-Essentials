# AWS Shared Responsibility Model

## Overview
In AWS Cloud, the responsibility of securing resources is shared between the customer and AWS. This model is known as the **Shared Responsibility Model**.

- **AWS Responsibilities**: Referred to as "security of the cloud."
- **Customer Responsibilities**: Referred to as "security in the cloud."

This model can be compared to the division of responsibilities between a **homebuilder** and a **homeowner**.

## Customer Responsibilities: Security in the Cloud
As a customer, you are responsible for the security of everything that you create and manage within the AWS Cloud.

### Key Responsibilities:
- **Content Management**:
  - Complete control over your content.
  - Decide which content to store on AWS and which AWS services to use.
  - Manage access rights to your content.

- **Security Management**:
  - Configure and manage security settings based on your company's operational and security needs.
  - Select, configure, and patch operating systems on Amazon EC2 instances.
  - Configure security groups, manage user accounts, and control access permissions.

## AWS Responsibilities: Security of the Cloud
AWS is responsible for the security of the infrastructure that runs all of the services offered in the AWS Cloud.

### Key Responsibilities:
- **Global Infrastructure**:
  - AWS operates, manages, and controls components at all layers of the infrastructure.
  - This includes the host operating system, virtualization layer, and physical security of data centers.

- **Security of Data Centers**:
  - **Physical Security**: Ensures the physical security of data centers where AWS services are hosted.
  - **Hardware and Software Infrastructure**: Maintains and secures the hardware and software.
  - **Network Infrastructure**: Secures the networking components.
  - **Virtualization Infrastructure**: Manages the virtualization layer.

### Compliance and Verification:
- AWS provides reports from third-party auditors to verify its compliance with various computer security standards and regulations.
