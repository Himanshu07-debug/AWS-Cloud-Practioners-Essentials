### `AWS Practice Essentials - Amazon EC2 Overview`

#### What is Amazon EC2?
- **Amazon EC2 (Elastic Compute Cloud)**: A service that provides virtual servers (instances) to host applications, offering raw compute capacity for various business needs.

#### Key Concepts:
1. **Client/Server Model**: 
   - Similar to a coffee shop example, where a client requests a service, the server processes it, and then responds.
   - Applicable to various industries like healthcare, manufacturing, insurance, and video content delivery.

2. **Virtual Servers with EC2**:
   - **Cost-Effective & Flexible**: Compared to owning physical servers, EC2 is more cost-efficient, quick to start, and scalable.
   - **AWS Managed**: AWS handles the data centers, hardware, security, and ensures servers are ready for use.

3. **Traditional vs. EC2 Setup**:
   - **Traditional**:
     - Requires purchasing hardware upfront, waiting for servers to delievered to you, setting up, securing, and maintaining physical servers.
     - Time-consuming and expensive, with a fixed investment.
   - **EC2**:
     - No upfront costs; pay only for the compute resources used.
     - Instances can be started and stopped as needed.

4. **Multitenancy & Virtualization**:
   - **Virtualization**: EC2 instances share physical host machines managed by AWS using a hypervisor.
   - **Multitenancy**: Multiple virtual machines (VMs) share the same physical resources but are isolated and secure.
   - **Hypervisor**: Manages resource allocation and ensures isolation between different VMs.

5. **EC2 Flexibility**:
   - **Instance Configuration**: Choose the operating system (Windows or Linux), software, and resources (CPU, memory).
   - **Resizable Instances**: Scale up (vertically) by adding more resources as needed.
   - **Networking Control**: Decide on the network settings, including public or private access.

6. **Benefits of EC2**:
   - **Rapid Provisioning**: Quickly spin up or terminate instances.
   - **Cost Efficiency**: Pay only for running instances.
   - **Enhanced Innovation**: Simplifies server acquisition, enabling faster development and deployment.

7. **Virtual Machines & EC2**:
   - Virtual machines are not new, but EC2's ease of use and cost-effectiveness make them more accessible for businesses and developers.

#### Conclusion:
- Amazon EC2 provides a robust, flexible, and cost-effective way to manage computing resources, allowing businesses to focus on innovation without worrying about underlying infrastructure.


#### `Amazon EC2 Instance Types`

When choosing an EC2 instance type, match it with your workload's needs—compute, memory, or storage.

#### 1. **General Purpose Instances**
- **Balanced Resources**: Offers a mix of compute, memory, and networking.
- **Use Cases**: 
  - Application servers
  - Gaming servers
  - Enterprise application backends
  - Small/medium databases
- **Best For**: Applications with balanced resource needs; no specific optimization required.

#### 2. **Compute Optimized Instances**
- **High-Performance Processors**: Ideal for compute-bound applications.
- **Use Cases**:
  - High-performance web servers
  - Compute-intensive application servers
  - Dedicated gaming servers
  - Batch processing of large transaction groups
- **Best For**: Workloads requiring high compute power.

#### 3. **Memory Optimized Instances**
- **Fast Memory Performance**: Designed for applications processing large datasets in memory.
- **Use Cases**:
  - High-performance databases
  - Real-time processing of large, unstructured data
- **Best For**: Workloads with high memory requirements.

#### 4. **Accelerated Computing Instances**
- **Hardware Accelerators**: Use coprocessors for functions like floating-point calculations, graphics processing, and data pattern matching.
- **Use Cases**:
  - Graphics applications
  - Game streaming
  - Application streaming
- **Best For**: Tasks that benefit from specialized hardware acceleration.

#### 5. **Storage Optimized Instances**
- **High IOPS Performance**: Optimized for workloads needing high, sequential read/write access to large datasets.
- **Use Cases**:
  - Distributed file systems
  - Data warehousing
  - High-frequency online transaction processing (OLTP)
- **Best For**: Applications requiring high input/output operations per second (IOPS).

#### Key Metrics:
- **IOPS (Input/Output Operations Per Second)**: Measures storage device performance. Higher IOPS means better performance for tasks needing quick data access.



#### `Scalability in AWS`

AWS offers significant advantages in scalability and elasticity, enabling businesses to adjust capacity based on demand, which is a major improvement over traditional on-premises data centers.

### The On-Premises Data Center Dilemma
1. **Varying Workloads:** Customer demand often fluctuates, whether over a 24-hour period or across different seasons.
2. **Hardware Investment Challenge**
3. **Average Load:** Purchasing for average usage minimizes wasted resources but can lead to shortages during peak demand.
4. **Peak Load:** Buying for the maximum load ensures customer satisfaction during peak times but results in underutilized resources most of the year.
5. **Utilization Issues:** Many data centers experience low average utilization, sometimes under 10%, due to the fear of missing peak demand.

### AWS Solution
1. **Provisioning to Demand:** AWS allows businesses to adjust capacity dynamically, matching resource allocation to current demand:
2. **Happy Customers:** Services are consistently available, even during peak times.
3. **Cost Efficiency:** Businesses only pay for the resources they use, maximizing ROI.

### Predictive scaling :
- Predictive Scaling automatically schedules the right number of Amazon EC2 instances based on predicted demand.
This is also called as `Disaster Planning.`

1. **Redundancy:** AWS supports creating redundant instances to prevent service disruption, ensuring high availability.
2. **No Single Point of Failure**

- **NOTE :** you can configure the minimum/ maximum capacity during setup


## Elastic Load Balancing (ELB)
- **Function**: Automatically distributes incoming traffic across multiple resources (e.g., Amazon EC2 instances).
- **Load Balancer**: Acts as a single point of contact for incoming web traffic.
- **Integration**: Works with Amazon EC2 Auto Scaling to ensure high performance and availability.
- **Example**:
  - **Low-Demand Period**: Few EC2 instances are running, matching the demand.
  - **High-Demand Period**: More EC2 instances are launched as demand increases, and traffic is evenly distributed.

## Messaging and Queuing

## Example: Coffee Shop Ordering System
- **Tightly Coupled System**:
  - **Process**: Cashier takes the order, passes it to the barista, who prepares the drink.
  - **Issue**: If the barista is unavailable, the process halts, causing delays.
- **Loosely Coupled System with SQS**:
  - **Process**: Cashier places the order in a queue (order board) (SQS) [ Concept of messaging and Queueing ]
  - **Benefit**: Cashier can continue taking orders while the barista retrieves and prepares them from the queue.
- **Loosely Coupled System with SNS**:
  - Can send the notification to all the subscribers that there coffee is ready, in one go.

- **Tightly Coupled**: Direct communication between components (e.g., cashier and barista).
  - **Issue**: If one component fails, the entire system is affected.
- **Loosely Coupled**: Introduces a buffer or queue (e.g., order board) between components.
  - **Benefit**: If one component fails, others continue to operate without disruption.
  - **AWS Services**:
    - **Amazon SQS - Simple Queue Service**: Sends, stores, and receives messages between software components.
      - **Queue**: Holds messages until they are processed.
      - **Scalability**: Automatically scales, reliable, and easy to use.
    - **Amazon SNS - Simple Notification Service**: Publish/subscribe service for sending notifications to multiple subscribers.
      - **SNS Topic**: Channel for message delivery.
      - **Subscribers**: Can be endpoints like SQS queues, Lambda functions, or HTTP/S webhooks.
      - **Notification Delivery**: Supports mobile push, SMS, and email.



## Monolithic vs. Microservices Architecture
- **Monolithic Applications**:
  - **Definition**: Tightly coupled components (e.g., databases, servers, UI, business logic).
  - **Issue**: If one component fails, others may fail, leading to a potential complete application failure.
- **Microservices**:
  - **Definition**: Loosely coupled components that operate independently.
  - **Benefit**: A single component failure does not affect the entire application.
  - **AWS Services**:
    - **Amazon SNS**: Sends messages to subscribers (e.g., web servers, email, Lambda functions).
    - **Amazon SQS**: Manages message queues for decoupled application components.



# AWS Serverless Computing & Containers

## Serverless Computing
- **Definition**: Code runs on servers without needing to provision or manage them.
- **Benefits**:
  - Focus on innovation, not server maintenance.
  - Automatic scaling based on demand (e.g., throughput, memory).
- **AWS Service**: **AWS Lambda**.
  - **How It Works**:
    1. Upload code to Lambda.
    2. Set triggers (e.g., AWS services, mobile apps, HTTP endpoints).
    3. Lambda runs code when triggered.
    4. Pay only for compute time used.
  - **Example**: Automatically resizing images when uploaded to the AWS Cloud.

## Containers
- **Definition**: Standard way to package application code and dependencies into a single object.
- **Benefits**:
  - Consistent environment across different systems.
  - Ideal for secure, reliable, and scalable workflows.
- **Examples**:
  - **Single Host with Multiple Containers**: Ensures consistent application environment, reducing debugging time.
  - **Multiple Hosts with Hundreds of Containers**: At scale, monitoring resources (memory, security, logging) becomes critical.
- **AWS Service**: **Amazon Elastic Container Service (ECS)**.
  - **Features**:
    - Scalable, high-performance container management.
    - Supports Docker containers.
    - Allows API calls to launch and stop Docker-enabled applications.


