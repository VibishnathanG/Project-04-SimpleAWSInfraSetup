# Project-04-SimpleAWSInfraSetup
This is Project Mainly concentrating on creating Simple Infra with AWS services


𝗛𝗮𝗽𝗽𝘆 𝘁𝗼 𝘀𝗵𝗮𝗿𝗲 𝗼𝗻𝗲 𝗼𝗳 𝗺𝘆 𝗽𝗿𝗼𝗷𝗲𝗰𝘁 𝗼𝗻 𝗰𝗹𝗼𝘂𝗱 𝘄𝗵𝗶𝗰𝗵 𝗺𝗮𝗶𝗻𝗹𝘆 𝗳𝗼𝗰𝘂𝘀 𝗼𝗻 𝗳𝗼𝗹𝗹𝗼𝘄𝗶𝗻𝗴 𝗔𝗪𝗦 𝘀𝗲𝗿𝘃𝗶𝗰𝗲𝘀. [ Project-04-AWSInfraSetup ]

➡ EC2 - Instance management and custom user data.

➡ Autoscaling groups - Launch Templates and Rules.

➡ IAM - Users, Groups, Policies.

➡ EFS - Network file storage and mounting to multiple instance.

➡ Load Balancer - Target groups based on ENV.

➡ Network - VPC, Subnets, IGW, SG's and other network components.

𝗦𝗶𝗺𝗽𝗹𝗶𝗳𝗶𝗲𝗱 𝗥𝗲𝗾𝘂𝗶𝗿𝗲𝗺𝗲𝗻𝘁: Design and execute an simple AWS infrastructure project focused on Auto Scaling Groups, IAM user policies, and instance management. Develop three Auto Scaling Groups (DevASG, OpsASG, FinanceASG) with specific instance tags. Create IAM users with policy restrictions based on Auto Scaling Group environments and console access limitations. Log in as EC2User to terminate resources and update launch template user data for web server deployment. Verify instance changes across existing and new instances.

𝗦𝘁𝗲𝗽𝘀:

1. 🚀 Create Auto Scaling Groups:
  - DevASG
  - OpsASG
  - FinanceASG

2. 🏷️ Tag Instances:
  - DevASG instances tagged with "env=DevASG"
  - OpsASG instances tagged with "env=OpsASG"
  - FinanceASG instances tagged with "env=FinanceASG"
 
3. 👩‍💼 Create IAM Users:
  - DevUser with DevASG permissions
  - OpsUser with OpsASG permissions
  - FinanceUser with FinanceASG permissions
  - EC2User with limited EC2 actions
 
4. 🔐 Assign IAM Policies:
  - DevUser can manage DevASG instances
  - OpsUser can manage OpsASG instances
  - FinanceUser can manage FinanceASG instances
  - EC2User can't use EC2 Instance Connect
 
5. 🖥️ Console Access:
  - Log in as EC2User and terminate resources
  - Update launch template user data for web server deployment
  - Attach EFS volume to instances as needed(Added in user data)
 
6.📄 User Data Step:
  - Add user data to launch template to mount EFS and deploy web server
  - Update index.html with custom messages for each instance group
  - Make sure changes in the web server are visible on new and existing instances
 
7. 🚀 Create ProdASG:
  - Create ProdASG with launch template
  - Ensure changes to launch template reflect on new and existing instances
 
8. 🛠️ Instance Management:
  - Terminate two instances from ProdASG
  - Verify changes in launch template user data on remaining instances
  - Verify EFS volume attachment on instances

9. ⚖ Load Balancer:
- Create LB for each ENV instance with the help of target group.
- Verify endpoint for correct maping.

10. ❌ Environment Cleanup:
- Clean up all the resource created, starting with ASG, LB, Instance, EFS, VPC and IAM's.
