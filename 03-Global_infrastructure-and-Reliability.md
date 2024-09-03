# Global Infrastructure and Reliability

## High Availability

Imagine you want to grab a coffee at a cafe, but today a parade is passing right in front of the shop. This is exciting, but it also means customers driving to the shop can't reach it, which could hurt sales and make them unhappy.

Luckily, our cafe has more than one location around the city. So, if one shop is blocked by a parade or a power outage, customers can still get their coffee at another nearby location. AWS does something similar with its global infrastructure to ensure high availability and fault tolerance.

Instead of having one big data center, which could fail due to a disaster, AWS has many data centers in different areas called Regions. This setup ensures that if one data center faces an issue, others can keep running, just like our cafe chain.

## Regions

When running an application or storing data, it needs a place to operate. Traditionally, businesses ran their applications in their own data centers, which came with the risk of being affected by disasters. If a disaster struck, you would lose access to your data center and face the challenges of maintaining another one, which is costly.

AWS solves this problem by creating Regions, which are groups of data centers around the world. These Regions are strategically placed to meet business traffic demands and are connected through a high-speed network controlled by AWS.

### Key Points about Regions:
1. **Compliance**: Choose a Region based on your compliance needs. For instance, if your data must stay within UK boundaries, use the London Region.
2. **Proximity**: The closer you are to your customers, the better, due to latency issues. Running applications close to your customer base is usually the best choice.
3. **Feature Availability**: Some Regions may not have all AWS features. New services may take time to be available in all Regions.
4. **Pricing**: Costs can vary between Regions due to factors like taxes. Choose a Region that balances cost and proximity to your customers.

## Availability Zones

Regions are made up of multiple data centers called Availability Zones (AZs). Each AZ is a separate data center with its own power, networking, and connectivity. When you launch an Amazon EC2 instance, it runs in an AZ.

To ensure your application can keep running even if a disaster hits one AZ, AWS recommends running instances in multiple AZs within a Region. These AZs are spread out to avoid being affected by the same disaster, but are close enough to communicate with low latency.

### Key Points about Availability Zones:
- **Redundancy**: Running your application in multiple AZs ensures that if one fails, others can take over.
- **Low Latency**: AZs are placed to maintain low latency communication.
- **Regional Services**: Some AWS services run across multiple AZs automatically, offering high availability without extra effort from you.

Running your application across multiple AZs and Regions ensures that it remains available even during unexpected events, just like our coffee shop chain.


### Regions and Proximity
- **Regions**: AWS has data centers worldwide, called Regions. When choosing a Region, proximity to your customers is important to reduce latency.
- **Customers Everywhere**: If your customers are spread out globally, use content delivery networks (CDNs) like **Amazon CloudFront** to cache and deliver data faster, closer to where they are.

### Edge Locations and AWS Outposts
- **Edge Locations**: These are places separate from Regions that help deliver content quickly to users globally. They also run services like **Amazon Route 53** (DNS) to direct traffic with low latency.
- **AWS Outposts**: If a business needs AWS services inside their own data center, AWS can set up a mini Region onsite, providing all AWS functionalities while staying local.

### Interacting with AWS
- **APIs**: Everything in AWS is controlled by APIs. These are predefined ways to interact with AWS services.
- **Tools**:
  - **AWS Management Console**: A browser-based tool for managing AWS resources visually. Good for beginners but less suited for automation. Also there can be chances of human mistake as it is done manually.
  - **AWS CLI (Command Line Interface)**: Allows you to make API calls through the terminal, enabling scripting and automation. You just write the Command, rest part AWS handles.
  - **AWS SDKs (software development kits)**: Let developers interact with AWS through programming languages, avoiding manual resource creation.
  
### Automation and Deployment
- **AWS Elastic Beanstalk**: Simplifies deploying applications by handling the infrastructure for you, allowing you to focus on your code.
- **AWS CloudFormation**: An infrastructure-as-code tool that lets you define AWS resources in text templates (JSON/YAML). It automates the provisioning of resources, ensuring consistent deployments with less room for error.

### Summary
- The AWS Management Console is great for learning but not ideal for automation.
- Use **CLI** for scripting, **SDKs** for programmatic interactions, and tools like **Elastic Beanstalk** and **CloudFormation** for automating and managing AWS environments efficiently.
