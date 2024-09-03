## Module 1

#### Mentors : 
  - Blaine Sundrud

### Client Server Model :

- All of modern computing uses a basic `client-server model`.

- In real life, for a shop, I make a request for coffee and the request was handled by the staff.

- In computing world, a client can be a web browser or desktop application that a person interacts with to make requests to computer servers. A server can be services such as in AWS, it can be `Amazon Elastic Compute Cloud (Amazon EC2)`, a type of **virtual server.**


### Key value of AWS :

- `Pay for What You Use.`

- Similar to staffing a coffee shop:
    - Employees are paid only for hours worked.
    - AWS works similarly— instances are billed only when active.

- `Scalability:`
    - Add or remove resources (e.g., instances) as needed.
    - Avoids overpaying for unused capacity.


### Cloud Computing :

- **Defination :** Cloud computing is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing.

- on-demand delivery : You dont need to tell in advance.. You have flexibility.. Demand came.. add more servers.. Demand gone.. remove them

- IT resources : Tasks that are common, repetative, time consuming.. AWS helps in that so that you can focus on unique things. (ex -> MySQL bnana is common, the way tables are made makes you unique)

- over the internet : accessible anywhere over a network

- pay-as-you-go-pricing : Key value of AWS


### Cloud Computing Deployment Models Strategies :

1. `Cloud-based Deployment`

- **Description**:
  - Run all parts of the application in the cloud.
  - Migrate existing applications or design new ones in the cloud.
- **Approach**:
  - Use low-level infrastructure (more management required) or high-level services (less management needed).
- **Example**:
  - An application with virtual servers, databases, and networking components all in the cloud.

2. `On-premises Deployment`
- **Description**:
  - Resources are deployed on-site, using virtualization and resource management tools.
- **Also Known As**: Private cloud deployment.
- **Benefits**:
  - Increases resource utilization.
  - Suitable for applications fully kept in your on-premises data center.
- **Example**:
  - Applications running entirely on your company's own data center, with enhanced management and virtualization.


### `Virtaulization :`

- Virtualization is the process of creating virtual versions of physical computer resources, like servers or storage, allowing multiple systems to run on a single physical machine. It helps in better resource utilization and flexibility.

- `multiple systems :`
    - In virtualization, one physical machine (like a server) can be divided into multiple virtual machines (VMs). Each VM operates like a separate, independent computer with its own operating system and applications. This allows multiple "systems" to run on a single physical hardware setup.
    - `Example :` a single CPU to be shared among multiple virtual machines. Each virtual machine can use part of the CPU's power as if it were its own. 

#### 3. `Hybrid Deployment`

- **Description**:
  - Connects cloud-based resources with on-premises infrastructure.
- **Use Cases**:
  - Legacy applications better maintained on-site.
  - Compliance with regulations that require certain data to be kept on premises.
- **Example**:
  - A company using cloud services for data processing and analytics while keeping legacy applications in their on-site data center.


### Benefits of Cloud Computing :

1. Cost for data centers, physical servers are made before use and then when the servers is running, you will be only charged for how much computation you use. Hence, saves cost by avoiding highly initial investments and allows for flexibility in resource usage.

2. Reduces the need for infrastructure management like data center management, allowing focus on applications and customers.

3. Quick development and deployment of applications allowing faster resource access, innovation as resources are quickly available to experiment.

4. Go global in minutes. low latency (reduced delays). Reach global customers quickly irrespective of their location.

5. No need to predict the infrastructure capacity.. AWS is auto-scaled



